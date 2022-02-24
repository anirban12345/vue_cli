<template>
  <table class="table table-bordered">
    <thead>
      <tr>
        <th>Name</th>        
        <th>Address</th>        
      </tr>
    </thead>
    <tbody :key="pdata.id" v-for="pdata in persondata">  
      <Pdata @pdata-activate="$emit('pdata-activate',pdata.id)" @pdata-delete="$emit('pdata-delete',pdata.id)" :pdata="pdata" />      
    </tbody>
  </table>
</template>

<script>

import Pdata from './Pdata.vue'

export default {
  name: 'Persondata',
  components: {      
    Pdata
  },  
  props: {
    persondata: Array,
  },  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
