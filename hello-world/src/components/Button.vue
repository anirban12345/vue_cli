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
    onClick()
    {
      //console.log('click');
      this.$emit('toggle-add-pdata')
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
``