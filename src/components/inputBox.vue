<template>
<div class="input-container">
  <h1>Tasks</h1>
  <form class="input-wrapper" @submit.prevent="addTodos">
    <input v-model="newTodo" id="userIn" ref="userinput" type="text" maxlength="30">
    <label for="userIn"></label>
    <button type="submit" class="btn">Add</button>
  </form>

  <div class="tasks-container">
  <ul>
    <li class="task" v-for="todo in todos" :class="{done: todo.done}" b>
      
      <p :class="{done: todo.done}">{{todo.title}}</p> 
      <div>
        <input type="checkbox" v-model='todo.done'>
        <i class="del far fa-trash-alt"></i>
        <i class="edit far fa-edit"></i>
      
      </div>
    
    </li>
  </ul>
   

</div>

</div>

</template>

<script>

export default {
  
  data () {
    return {
      newTodo:'',
      todos:[]
     
    }
  },
  methods:{
    addTodos(){
      this.todos.push({
        title: this.newTodo,
        done:false
      })
      this.newTodo=''
    }
   
  }
  
}
</script>

<style scoped>
.input-container{
 display: grid;
  place-items: center;
  border-bottom: 1px solid white;
  padding:1em 0em;
  
}
h1{
  color: white;
}
.btn{
  
  border: 1px solid white;
  padding: .1em 1em;
  cursor: pointer;
  transition: all 250ms ease-in-out;
}
.btn:hover{
background: white;
color: #290149;;
}
.input-wrapper{
  width: 60%;
  text-align: center;
}
input{
  width: 70%;
}
.tasks-container{

  width: 80%;
  height: 40vh;
  margin: 1em;
  display: grid;
  padding: .5em;
  margin: 1em auto;
  
  
}
ul{
  overflow-y: auto;
}

.task{
  list-style: none;
  background: white;
  padding-inline: .5em;
  border-radius: 2px;
  display: flex;
  align-items:baseline ;
  justify-content: space-between;
  margin-bottom: .5em;

}
.task div{
  
  width: 25%;
  margin-inline:.5em ;
  display: flex;
  gap: .5em;
  justify-content: center;
}
.task i {

  cursor: pointer;
  transition: all 250ms ease-in-out;
    
}
.del:hover{
  color: red;
}
.edit:hover{
  color: green;
}

.done{
  text-decoration: line-through;
  opacity: .5;
}

</style>