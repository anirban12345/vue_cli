<template>  
  <button @click="onCLick()" class={{classname}}>{{text}}</button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    text: String,
    classname: String
  },
  methods:{
    onCLick()
    {
      console.log(this.text);
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
