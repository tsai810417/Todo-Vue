<template lang="html">
  <div>
    <!-- refactor the todo component -->
    <todo v-for="(todo, index) in todos"
    v-bind:todo="todo"
    v-bind:index="index"
    v-bind:key="index"
    v-on:reverse-status="reverseStatus"
    v-on:delete-todo="deleteTodo"></todo>
    <!-- <div class="centered card" v-for="(todo,idx) in todos" v-bind:key="idx">
      <div class="content">
        <div class="header">
          {{ todo.title }}
        </div>
        <div class="meta">
          {{ todo.project }}
        </div>
        <div v-show="todo.done">
          Completed
        </div>
        <div v-show="!todo.done">
          Incomplete
        </div>
      </div>
    </div> -->
  </div>
</template>

<script type="text/javascript">
import Todo from './Todo';

export default {
  props: ['todos'],
  components: {
    Todo,
  },
  methods: {
    reverseStatus(idx) {
      this.todos[idx].done = !(this.todos[idx].done);
    },
    deleteTodo(idx) {
      this.todos.splice(idx, 1);
    },
  },
};
</script>

<style lang="css">
  .centered-card {
    width: 300px;
    height: 100px;
  }
  .content {
    width: inherit;
    height: inherit;
    margin: 10px;
    border: 1px solid #000000
  }
  .header, .meta, .status {
    margin: 5px;
  }
  .buttons {
    margin: 5px;
  }
</style>
