<template>
  <div class="centered card">
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
  <!-- <div class="content" v-if="isEditing">
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
        <button type="button" v-on:click="hideForm">Close X</button>
      </div>
    </div>
  </div> -->
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
    showForm(){
      this.isEditing = true;
    },
    hideForm(){
      this.isEditing = false;
    },
  },
};
</script>
