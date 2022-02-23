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
  data(){
        return {
            text:this.text,
            classname:this.classname
        }
  }, 
  methods:{
    async onCLick()
    {
      console.log(this.text);
      if(this.text=="Activate")
      {
        this.text="Deactivate";
        this.classname="btn btn-danger btn-sm";
      }
      if(this.text=="Deactivate")
      {
        this.text="Activate";
        this.classname="btn btn-success btn-sm";
      }
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css');
</style>
