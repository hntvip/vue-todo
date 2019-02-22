<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- <router-view/> -->
    <todo-list :todos="todos"></todo-list>
    <create-todo v-on:create-new="createTodo"></create-todo>
  </div>
</template>

<script>
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';
export default {
  name: 'App',
  components:{
    TodoList,
    CreateTodo
  },
  data() {
    return {
      todos: [{
        id: 1,
        title: 'Todo A',
        project: 'Project A',
        done: false
      }]
    }
  },
  methods: {
    createTodo(todo){
      const id = this.todos.length + 1;
      this.todos.push({
        'id': id,
        'title': todo.title,
        'project': todo.project,
        'done': todo.done,
      })
    }
  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
