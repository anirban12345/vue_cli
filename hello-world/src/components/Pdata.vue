<template>  
      <tr :class="[pdata.active ? 'alert-success' : 'alert-danger']">
        <td>{{pdata.name}}</td>
        <td>{{pdata.address}}</td>
        <td><Button :class="classname" :text="text" /></td>
      </tr>
</template>

<script>

import Button from './Button.vue'
export default {
  name: 'Pdata',  
  components: {     
    Button    
  },
  props: {
    text: String,
    classname: String,
    pdata: Object,
  },
  data(){
        return {
            text:"Activate",
            classname:'btn btn-danger btn-sm'            
        }
  },  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css');
</style>
