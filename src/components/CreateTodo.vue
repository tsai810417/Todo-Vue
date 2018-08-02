<template>
  <div class="centered-card">
    <div class="add-icon" v-if="!isCreating">
      <p>+</p>
    </div>
    <div class="creat-form" v-if="isCreating">

    </div>
  </div>
</template>

<script>
export default {
  props: ['todo'],
  data() {
    return {
      isCreating: false,
    };
  },
  methods: {
    openForm() {

    },
    closeForm() {

    },
    sendForm() {

    },
  },
};
</script>

<style lang="css">
</style>
