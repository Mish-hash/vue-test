<template>
  <div>
    <h2>Add todo</h2>
    <router-link to="/">Home</router-link>
    <hr>
    
    <AddTodo
      @add-todo="addTodo"
    />
    <h2>Todo list</h2>
    <Loader v-if="loading" />
    <TodoList 
        v-else-if="todos.length"
        v-bind:todos="todos"
        @remove-todo="removeTodo"
    />
    <p v-else>NO Todos</p>
  </div>
</template>

<script>
import TodoList from '@/components/TodoList';
import AddTodo from '@/components/AddTodo';
import Loader from '@/components/Loader';

export default {
  name: 'App',
  data() {
    return {
        todos: [],
        loading: true
    }
  },
  components: {
    TodoList,
    AddTodo,
    Loader,
  },
  mounted(){
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=3')
      .then(response => response.json())
      .then(json => {
        this.todos = json
        this.loading = false
      })
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id);
    },
    addTodo(todo) {
      this.todos.push(todo)
    }
  },
};
</script>
