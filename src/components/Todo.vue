<template>
  <div class="centered-card">
    <div class="content" v-show="!isEditing">
      <div class="header">
        {{ todo.title }}
      </div>
      <div class="meta">
        {{ todo.project }}
      </div>
      <p class="status"
      v-if="todo.done"
      v-on:click="reverseStatus(index)">
        Completed
      </p>
      <p class="status"
      v-if="!todo.done"
      v-on:click="reverseStatus(index)">
        Incomplete
      </p>
      <div class="buttons">
        <button v-on:click="deleteTodo(index)">Delete</button>
        <button v-on:click="showForm">Edit</button>
      </div>
    </div>
    <div class="content" v-show="isEditing">
      <div class="ui form">
        <div class="field">
          <label>Title
            <input type="text" v-model="todo.title">
          </label>
        </div>
        <div class="field">
          <label>Project
            <input type="text" v-model="todo.project">
          </label>
        </div>
        <div class="close button">
          <button type="button" v-on:click="hideForm">Done</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['todo', 'index'],
  data() {
    return {
      isEditing: false,
    };
  },
  methods: {
    reverseStatus(index) {
      this.$emit('reverse-status', index);
    },
    deleteTodo(index) {
      this.$emit('delete-todo', index);
    },
    showForm() {
      this.isEditing = true;
    },
    hideForm() {
      this.isEditing = false;
    },
  },
};
</script>
