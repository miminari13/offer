<script setup lang="ts">
  import Nav from './Nav.vue';
  import Workspace from './Workspace.vue';
</script>

<template>
  <div class="dashboard">
    <Nav />
    <Workspace /> 
  </div>
</template>

<style scoped>
  .dashboard {
    display: flex;
    height: 100vh;
    min-width: 1200px;
    min-height: 800px;
  }
</style>