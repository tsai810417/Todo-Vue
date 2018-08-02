<template>
  <div class="centered-card">
    <div class="content" v-show="!isEditing">
      <div class="header">
        {{ todo.title }}
      </div>
      <div class="meta">
        {{ todo.project }}
      </div>
      <p class="status" v-if="todo.done">
        Completed
      </p>
      <div class="buttons">
        <button v-on:click="deleteTodo">Delete</button>
        <button v-on:click="showForm">Edit</button>
      </div>
      <p class="status" v-if="!todo.done">
        Incomplete
      </p>
    </div>
    <div class="content" v-show="isEditing">
      <div class="ui form">
        <div class="field">
          <label>Title</label>
          <input type="text" v-model="todo.title">
        </div>
        <div class="field">
          <label>Project</label>
          <input type="text" v-model="todo.project">
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
  props: ['todo'],
  data() {
    return {
      isEditing: false,
    };
  },
  methods: {
    deleteTodo() {

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
