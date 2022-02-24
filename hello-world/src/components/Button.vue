<template>  
  <button @click="onClick()" class={{classname}}>{{text}}</button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    text: String,
    classname: String
  },  
  methods:{
    
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css');
</style>
