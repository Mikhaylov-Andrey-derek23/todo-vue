<template>
  <div id="app">
    <h1>Todo applacation</h1>
    <hr>
    <addItem  @addTodo = "addTodo"/>
    <select v-model="filter">
      <option value="all">All</option>
      <option value="completed">Completed</option>
      <option value="not-completed">Not completed</option>
    </select> 
    <ToDoList v-bind:todos = "filterTodos"
    @remove-todo = "remove"
    />
  </div>
</template>

<script>

import ToDoList from "@/components/toDoList";
import addItem from "@/components/addItem";
export default {
  name: 'App',
  components: {
    ToDoList,
    addItem
  },
      data(){
      return{
        todos : [
          {
            id : 1,
            title : "Купить хлеб",
            completed : true
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
          
        ],
        filter : 'all'
      }
    }, 

    methods : {
      remove(id){
        this.todos = this.todos.filter(e => e.id != id);
      },
      addTodo(todo){
        this.todos.push(todo)
      }
    },

    watch : {
      filter(value){
        console.log(value)
      }
    },

    computed : {
      filterTodos(){
        if(this.filter === 'all'){
          return this.todos
        }
        else if(this.filter === 'completed'){
          return this.todos.filter(t => t.completed)
        }
        else if(this.filter === 'not-completed'){
          return this.todos.filter(t => !t.completed)
        }
        else{
          return this.todos
        }
      }
    }

}
</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

select{
  margin: .5rem 0;
  padding: .4rem;
}
</style>
