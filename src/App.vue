<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todos';


export default {
  name: 'App',
  components: {
    Todos
  },
  data(){
    return {
      todos:[
        {
          id:1,
          title:"Todo One",
          completed:true
        },
        {
          id:2,
          title:"Todo Two",
          completed:true
        },
        {
          id:3,
          title:"Todo three",
          completed:false
        }
      ]
    }
  },
  methods:{
    deleteTodo(id){
      console.log(id);
      this.todos = this.todos.filter(todo=>todo.id !== id);
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover {
    background: #666;
  }
</style>
