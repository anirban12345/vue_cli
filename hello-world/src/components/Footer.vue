<template>  
  <footer class="text-center">    
    <p> Copyright &copy; 2022</p> 
    <a href="/about">About</a>
  </footer>
</template>

<script>

export default {
  name: 'Footer',
  props: {
    title: String,
    showAddData:Boolean
  },
  components:{

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
