<template>  
  <div class="row">
    <div class="col-12">
      <div class="card">
        <form @submit="onSubmit">
          <div class="card-body"> 
              <h4>Enter Details</h4>  
              <hr />       
              <div class="form-group">
                <label for="name">Name:</label>
                <input type="text" v-model="name" class="form-control" id="name" placeholder="Enter Name" name="name">
              </div>
              <div class="form-group">
                <label for="address">Address</label>
                <input type="text" v-model="address" class="form-control" id="address" placeholder="Enter Address" name="address">
              </div>     
              <button type="submit" class="btn btn-success btn-block">Save</button>  
          </div>                  
        </form>                   

      </div>
    </div>
  </div>
</template>

<script>
import Button from './Button.vue'

export default {
  name: 'Adddata',
  components: {      
    Button
  },
  props: {
    title: String
  },
  data()
  {
    return {
      name:'',
      address:'',
      active:false
    }
  },
  methods:{
    onSubmit(e)
    {
      e.preventDefault();

      if(!this.name)
      {alert("Please fill the data"); return;}

      const newPdata={
        id:Math.floor(Math.random()*1000),
        name:this.name,
        address:this.address,
        active:this.active
      }

      //console.log(newPdata);

      this.$emit('pdata-add',newPdata)

      this.name=''
      this.address=''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
