<template>  
      <tr>
        <td>{{pdata.name}}</td>
        <td>{{pdata.address}}</td>
      </tr>
</template>

<script>
export default {
  name: 'Pdata',    
  props: {
    pdata: Object,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
