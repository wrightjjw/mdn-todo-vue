<template>
  <div id="app">
    <h1>To-Do List</h1>
    <ToDoForm @todo-added="addToDo"></ToDoForm>
    <ul>
      <li v-for='item in ToDoItems' :key='item.id'>
        <ToDoItem :label='item.label' :done='item.done' :id='item.id'/>
      </li>
    </ul>
  </div>
</template>

<script>
import uniqueId from 'lodash.uniqueid';

import ToDoItem from './components/TodoItem';
import ToDoForm from './components/TodoForm';

export default {
  name: 'App',
  components: {
    ToDoItem,
    ToDoForm,
  },
  data() {
    return {
      ToDoItems: [
        { id: uniqueId('todo-'), label: 'Learn Vue', done: false },
        { id: uniqueId('todo-'), label: 'Create a Vue project with the CLI', done: true },
        { id: uniqueId('todo-'), label: 'Have fun', done: true },
        { id: uniqueId('todo-'), label: 'Create a to-do list', done: false },
      ],
    };
  },
  methods: {
    addToDo(toDoLabel) {
      this.ToDoItems.push({ id: uniqueId('todo-'), label: toDoLabel, done: false });
    }
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
