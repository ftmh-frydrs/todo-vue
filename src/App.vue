<template>
  <TodoList></TodoList>
</template>

<script>

import './assets/tailwind.css';
import TodoList from './components/TodoList.vue';

export default {
  name: 'App',
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
