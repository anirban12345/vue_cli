<template>  
  <header>    
    <h2>Welcome {{title}} </h2>
    <button type="button" class="btn btn-info btn-sm">Add New Data</button>
    <br />
  </header>
</template>

<script>
import Button from './Button.vue'
export default {
  name: 'Header',
  props: {
    title: String
  },
  component:{
    Button
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
