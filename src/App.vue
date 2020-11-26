<template>
  <div id="app">
    <h1>First project on Vue.js</h1>
    <h2>Add todo</h2>
    <AddTodo
      @add-todo="addTodo"
    />
    <h2>Todo list</h2>
    <TodoList 
      v-bind:todos="todos"
      @remove-todo="removeTodo"
    />
  </div>
</template>

<script>
import TodoList from '@/components/TodoList';
import AddTodo from '@/components/AddTodo';

export default {
  name: 'App',
  data() {
    return {
      todos: [
        /* {id: 1, title: "некиавлдо ва", completed: false},
        {id: 2, title: "оырчалбсмдпкблпсж ", completed: false},
        {id: 3, title: "лаождвыопждвло ", completed: false},
        {id: 4, title: "вапрпыврсмрвенсми ипарпт ", completed: false},
        {id: 5, title: "паыр  твар твапит рпар ", completed: false},
        {id: 6, title: "пар тптв ввпт  ", completed: false},
        {id: 7, title: "парт твпаыт авт ", completed: false},
        {id: 8, title: "некиадло ррд рд влдо ", completed: false}, */
      ]
    }
  },
  components: {
    TodoList,
    AddTodo,
  },
  mounted(){
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=3')
      .then(response => response.json())
      .then(json => {
        this.todos = json
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

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
