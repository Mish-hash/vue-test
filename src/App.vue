<template>
  <div id="app">
    <h1>First project on Vue.js</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aliquam aliquid non consequuntur quaerat, 
      nihil sequi necessitatibus totam, explicabo fuga animi expedita corrupti molestias ea debitis 
      repudiandae provident perspiciatis itaque magnam.
    </p>
    <hr>
    <TodoList v-bind:todos="todos"/>
  </div>
</template>

<script>
import TodoList from '@/components/TodoList'

export default {
  name: 'App',
  data() {
    return {
      todos: [
        {id: 1, text: "некиавлдо ва", completed: false},
        {id: 2, text: "оырчалбсмдпкблпсж ", completed: false},
        {id: 3, text: "лаождвыопждвло ", completed: false},
        {id: 4, text: "вапрпыврсмрвенсми ипарпт ", completed: false},
        {id: 5, text: "паыр  твар твапит рпар ", completed: false},
        {id: 6, text: "пар тптв ввпт  ", completed: false},
        {id: 7, text: "парт твпаыт авт ", completed: false},
        {id: 8, text: "некиадло ррд рд влдо ", completed: false},
      ]
    }
  },
  components: {
    TodoList,
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
