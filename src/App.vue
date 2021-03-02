<template>
<div class="container">
  
<app-searchBox></app-searchBox>
<app-tasks></app-tasks>
  

</div>

</template>

<script>
import inputbox from './components/inputBox'
import tasks from './components/tasks'

export default {
  
  components:{
    'app-searchBox': inputbox,
    'app-tasks': tasks
  },
  data () {
    return {
      
    }
  }
  
}
</script>

<style>
body{
  width: 100%;
  height: 100vh;
  display: grid;
  place-items: center;
  background: #290149;
  
}
.container{
  width: 40%;
  height: 70vh;
  border: 2px solid white;
  border-radius: 5px;
  
  
  

  
}

</style>
