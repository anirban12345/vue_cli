<template>  
      <tr :class="[pdata.active ? 'alert-success' : 'alert-danger']">
        <td>{{pdata.name}}</td>
        <td>{{pdata.address}}</td>
        <td>
          <div @click="$emit('pdata-delete',pdata.id)" class="btn btn-danger btn-sm text-white">Delete</div>
        </td>
      </tr>
</template>

<script>
export default {
  name: 'Pdata',    
  props: {    
    pdata: Object,
  },   
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
