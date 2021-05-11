<template>
  <div id="app">
    <h1>todo application</h1>
    <hr>
    <router-view/>
  </div>
</template>

<script>
// import TodoList from '@/components/TodoList';
// import AddTodoItem from '@/components/AddTodoItem';

export default {
  name: 'App',
  data() {
    return {
      todos: [
        // {id: 1, title: 'Something', completed: false },
        // {id: 2, title: 'Anything', completed: false },
        // {id: 3, title: 'Everything', completed: false },
      ]
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=3')
    .then(response => response.json())
    .then(json => this.todos = json)
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((item) => item.id !== id)
    },
    addTodo(newTodo) {
      this.todos.push(newTodo)
    }
  },
  components: {
    // TodoList,
    // AddTodoItem
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
