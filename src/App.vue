<template>
  <div class="container mt-4">
    <div class="row justify-content-center">
      <div class="col-6">
        <tarea-app />
      </div>
    </div>
  </div>
</template>

<script>
  import TareaApp from "./components/TareaApp.vue";

  export default {
    components: { TareaApp },
    name: 'App',
  }
</script>

<style>
  @import './assets/styles/style.css';
</style>