<template>
  <div id="app">
    <h1>Todo applacation</h1>
    <hr>
    <ToDoList v-bind:todos = "todos"/>
  </div>
</template>

<script>

import ToDoList from "@/components/toDoList";
export default {
  name: 'App',
  components: {
    ToDoList
  },
      data(){
      return{
        todos : [
          {
            id : 1,
            title : "Купить хлеб",
            completed : false
          },
          {
            id : 2,
            title : "Купить молоко",
            completed : false
          },
          {
            id : 3,
            title : "Купить масло",
            completed : false
          }
          
        ]
      }
    }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
