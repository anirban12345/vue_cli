<template>  
  <header>    
    <h2>Welcome {{title}} </h2>
    <Button @toggle-add-pdata="$emit('toggle-add-pdata')" :class="showAddData?'btn btn-danger btn-sm':'btn btn-info btn-sm'" :text="showAddData?'Close':'Add New Data'" />
    
  </header>
</template>

<script>
import Button from './Button.vue'
export default {
  name: 'Header',
  props: {
    title: String,
    showAddData:Boolean
  },
  components:{
    Button
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
