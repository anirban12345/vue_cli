<template>

<div class="container-fluid">
  <Header title="Home"/>

  <div v-show="showAddData">
    <Adddata @pdata-add="pdataAdd" />
  </div>

  <br />
  <Persondata @pdata-activate="pdataActivate" @pdata-delete="pdataDelete" :persondata="persondata" />  
</div>
  
</template>

<script>
import Header from './components/Header.vue'
import Adddata from './components/Adddata.vue'
import Button from './components/Button.vue'
import Persondata from './components/Persondata.vue'

export default {
  name: 'App',
  components: {  
    Header,
    Adddata,
    Button,
    Persondata
  },
  data()
  {
    return {
      persondata:[],
      showAddData: true
    }
  },
  methods:
  {
    pdataDelete(id)
    {
        //console.log('task ',id);
        if(confirm("Are Your Sure?")){
          this.persondata=this.persondata.filter((pdata)=>pdata.id!==id)
        }        
    }, 
    pdataActivate(id)   
    {
      //console.log('task ',id);
      this.persondata=this.persondata.map((pdata)=>pdata.id===id?{...pdata,active:!pdata.active}:pdata)
    },
    pdataAdd(pdata)
    {
      this.persondata=[...this.persondata,pdata]
    }
  },
  created()
  {
    this.persondata=[
        {
          id:"1",
          name:"Anirban",
          address:"Barabazar",
          active:true
        },
        {
          id:"2",
          name:"Gargi",
          address:"Dakhineswar",
          active:false
        },
    ]
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
@import url('https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css');


</style>
