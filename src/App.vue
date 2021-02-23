<template>
  <div id="app">
    <h1>To-Do List</h1>
    <ul>
      <li>
        <ToDoItem label='My ToDo Item' :done='true'/>
      </li>
    </ul>
  </div>
</template>

<script>

import ToDoItem from './components/TodoItem';

export default {
  name: 'App',
  components: {
    ToDoItem,
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
