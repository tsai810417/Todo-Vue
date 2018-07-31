<template lang="html">
  <div>
    <div class="centered card" v-for="todo in todos" v-bind:key="todo.id">
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
    </div>
  </div>
</template>

<script type="text/javascript">
export default {
  props: ['todos'],
};
</script>

<style lang="css">
</style>
