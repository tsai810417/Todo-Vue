<template>
  <div class="centered-card">
    <div class="add-icon" v-if="!isCreating">
      <p v-on:click="openForm">+</p>
    </div>
    <div class="creat-form" v-if="isCreating">
      <label>Title
        <input type="text" v-model="titleText">
      </label>
      <label>Project
        <input type="text" v-model="projectText">
      </label>
      <button type="button" v-on:click="sendForm">Create</button>
      <button type="button" v-on:click="closeForm">Cancel</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      titleText: '',
      projectText: '',
      isCreating: false,
    };
  },
  methods: {
    openForm() {
      this.isCreating = true;
    },
    closeForm() {
      this.isCreating = false;
      this.titleText = '';
      this.projectText = '';
    },
    sendForm() {
      let title = this.titleText;
      let project = this.projectText
      this.$emit('create', { title, project, done: false });
      this.titleText = '';
      this.projectText = '';
      this.isCreating = false;
    },
  },
};
</script>

<style lang="css">
</style>
