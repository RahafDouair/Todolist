
<template>
  <main>
<div class="homePage">
  <h3>Add New Todo </h3>

<form action="" @submit.prevent="addTodo">
<input class="todo" v-model="todoObject.text" type="text" placeholder="Enter Your Todos">
<br>
<input type="date" v-model="todoObject.from" name="" id="" placeholder="Form" class="my-2">
<input type="date" v-model="todoObject.to" name="" id="" placeholder="to" class="m-2 ">
<br>
<input type="submit" value ="add">

  
</form>
</div>
  </main>
</template>
<script setup>
import MyNav from '../components/MyNav.vue';
import {ref ,onMounted } from 'vue';

//data
const todos=ref([]);
const todoObject=ref({
  id:"",
  text:" ",
  from:" ",
  to:" ",
  createdAt:" ",
})
//methods
const addTodo=()=>{
  todoObject.value.id=todos.value.length + 1;
  todos.value.createdAt=new Date();
  todos.value.push(todoObject.value);
  localStorageTo();
    alert('Todos added Successfully');

  
  todoObject.value={
    id:'',
  text:" ",
  from:" ",
  to:" ",
  createdAt:" "
};
  console.log(todos.value);
};
const localStorageTo=()=>{
localStorage.setItem("todos" ,JSON.stringify(todos.value));
};
const updateTodos=()=>{
// localStorage.setItem("todos" ,JSON.stringify(todos.value));
if(localStorage.getItem("todos")){
  todos.value=JSON.parse(localStorage.getItem("todos"))
}
};
onMounted(() => {
  updateTodos();
})
</script>
<style  >

  .todo{
 width:50%;
 outline:none
  }
  .homePage {
    margin: 40px 0px 39px 48px !important;
}
input[type="submit"]{
  background: #57C389;
    border: none;
    padding: 3px 36px;
    color: white;
}

</style>

