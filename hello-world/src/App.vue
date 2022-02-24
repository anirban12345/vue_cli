<template>

<div class="container-fluid">
  <Header @toggle-add-pdata="toggleAddPdata" title="Home" :showAddData="showAddData"/>
  <br />
  <div v-show="showAddData">
    <Adddata @pdata-add="pdataAdd" />
    <br />  
  </div>
  
  <Persondata @pdata-activate="pdataActivate" @pdata-delete="pdataDelete" :persondata="persondata" />  

  <router-view></router-view>
  
  <Footer />
</div>
  
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Adddata from './components/Adddata.vue'
import Button from './components/Button.vue'
import Persondata from './components/Persondata.vue'

export default {
  name: 'App',
  components: {  
    Header,
    Footer,
    Adddata,
    Button,
    Persondata
  },
  data()
  {
    return {
      persondata:[],
      showAddData: false
    }
  },
  methods:
  {
    async pdataDelete(id)
    {
        //console.log('task ',id);
        if(confirm("Are Your Sure?")){
          const res=await fetch(`api/persondata/${id}`,{
          method:'DELETE',          
          })
          res.status==200 ?(this.persondata=this.persondata.filter((pdata)=>pdata.id!==id)):alert('Error deleting task')
        }        
    }, 
    async pdataActivate(id)   
    {
      //console.log('task ',id);
      const activate=await this.fetchPData(id);
      const updPdata={...activate,active:!activate.active}
      const res=await fetch(`api/persondata/${id}`,{
          method:'PUT',
          headers:{'Content-type':'application/json',},
          body:JSON.stringify(updPdata),
      })
      const data=await res.json()
      //console.log(data);
      this.persondata=this.persondata.map((pdata)=>pdata.id===id?{...pdata,active:data.active}:pdata)
    },
    async pdataAdd(pdata)
    {
      const res=await fetch('api/persondata',{
          method:'POST',
          headers:{'Content-type':'application/json'},
          body:JSON.stringify(pdata)
      })
      const data=await res.json()
      this.persondata=[...this.persondata,data]
    },
    toggleAddPdata()
    {
      this.showAddData=!this.showAddData
    },
    async fetchPersonData()
    {
      const res=await fetch('api/persondata')
      const data=await res.json()
      return data;
    },
    async fetchPData(id)
    {
      const res=await fetch(`api/persondata/${id}`);
      const data=await res.json();
      return data;
    }
  },
  async created()
  {
    this.persondata=await this.fetchPersonData()
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
@import url('https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css');


</style>
