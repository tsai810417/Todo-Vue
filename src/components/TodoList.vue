<template lang="html">
  <div>
    <!-- refactor the todo component -->
    <todo v-for="(todo, index) in todos"
    v-bind:todo="todo"
    v-bind:index="index"
    v-bind:key="index"></todo>
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
};
</script>

<style lang="css">
</style>
