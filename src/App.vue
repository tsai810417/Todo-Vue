<template>
  <div id="app">
    <p class="countTasks">
      Completed Tasks: {{ todos.filter(todo => {  return todo.done === true }).length }}
    </p>
    <p class="countTasks">
      Incompleted Tasks: {{ todos.filter(todo => {  return todo.done === false }).length }}
    </p>
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:create="create"></create-todo>
  </div>
</template>

<script>
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo,
  },
  data() {
    return {
      todos: [{
        title: 'Todo A',
        project: 'Project A',
        done: false,
      }, {
        title: 'Todo B',
        project: 'Project B',
        done: true,
      }, {
        title: 'Todo C',
        project: 'Project C',
        done: false,
      }, {
        title: 'Todo D',
        project: 'Project D',
        done: false,
      }],
    };
  },
  methods: {
    create(todoParams) {
      let newTodo = new Object();
      newTodo.title = todoParams.title;
      newTodo.project = todoParams.project;
      newTodo.done = todoParams.done;
      this.todos.push(newTodo);
    },
  },
};

</script>

<style>
  #app {
    display: flex;
    align-items: center;
    flex-direction: column;
  }
</style>
