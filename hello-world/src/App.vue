<template>

<div class="container-fluid">
  <Header title="Home"/>
  
  <div class="row">
    <div class="col-12">
      <div class="card">
        <div class="card-header">
          <h5>Enter Details</h5>
        </div>
        <div class="card-body">
            <div class="form-group">
              <label for="name">Name:</label>
              <input type="text" class="form-control" id="name" placeholder="Enter Name" name="name">
            </div>
            <div class="form-group">
              <label for="address">Address</label>
              <input type="text" class="form-control" id="address" placeholder="Enter Address" name="address">
            </div>            
        </div>        
        <div class="card-footer">
          <Button class="btn btn-success btn-sm" text="Save" />
          &nbsp;<Button class="btn btn-info btn-sm" text="Edit" />
          &nbsp;<Button class="btn btn-danger btn-sm" text="Delete" />
        </div> 

      </div>
    </div>
  </div>
  <br />
  <Persondata @pdata-delete="pdataDelete" :persondata="persondata" />  
</div>
  
</template>

<script>
import Header from './components/Header.vue'
import Button from './components/Button.vue'
import Persondata from './components/Persondata.vue'

export default {
  name: 'App',
  components: {  
    Header,
    Button,
    Persondata
  },
  data()
  {
    return {
      persondata:[]
    }
  },
  methods()
  {
    pdataDelete(id)
    {
        console.log('task ',id);
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
          active:true
        },
    ]
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
@import url('https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css');


</style>
