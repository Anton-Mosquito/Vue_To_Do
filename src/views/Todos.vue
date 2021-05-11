<template>
  <div>
    <h2>Todo application</h2>
    <router-link to="/">Home</router-link>
    <hr>
    <AddTodoItem
     @add-todo="addTodo"
    />
    <select v-model="filter">
      <option value="all">All</option>
      <option value="completed">Completed</option>
      <option value="not-completed">Not Completed</option>
    </select>
    <hr>
    <Loader v-if="loading"/>
    <TodoList
      v-else-if="filteredTodos.length"
      v-bind:todos="filteredTodos"
      @remove-todo="removeTodo"
    />
    <p v-else>No todos!</p>
  </div>
</template>


<script>
import TodoList from '@/components/TodoList';
import AddTodoItem from '@/components/AddTodoItem';
import Loader from '@/components/Loader';

export default {
  name: 'App',
  data() {
    return {
      todos: [
        // {id: 1, title: 'Something', completed: false },
        // {id: 2, title: 'Anything', completed: false },
        // {id: 3, title: 'Everything', completed: false },
      ],
      loading: true,
      filter: 'all'
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=3')
    .then(response => response.json())
    .then(json =>{
        setTimeout(() => {
             this.todos = json;
             this.loading = false;
        }, 2000);
       
        })
  },
  // watch: {
  //   filter(value) {
  //     console.log(value)
  //   }
  // },
  computed: {
    filteredTodos() {
      let array;
      if (this.filter === 'all'){ 
        array = this.todos
      }
      if (this.filter === 'completed'){ 
        array =  this.todos.filter((item)=> item.completed)
      }
      if (this.filter === 'not-completed'){ 
        array =  this.todos.filter((item)=> !item.completed)
      }

      return array;
    }
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
    TodoList,
    AddTodoItem,
    Loader
  }
}
</script>
