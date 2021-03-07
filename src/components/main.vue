<template>
<div>
  <button @click="changeName"> submit</button>
<h1>{{name}}</h1>
</div>
</template>

<script>
export default {
  
  data () {
    return {
      name: 'anthony'
      
    }
  },
  methods:{
    changeName(){

    }
  }
}
</script>

<style>


</style>
