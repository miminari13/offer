<script setup lang="ts">
  import Header from './Header.vue';
  import { ref } from 'vue';

  const today = ref('Aug 19')
</script>

<template>
  <div class="header">
    <div class="today">{{ today }}</div>  
  </div>
</template>

<style scoped>
  .today {
    font-size: 2rem;
    position: relative;
    display: inline-block;
  }

  .today:before {
    position: absolute;
    content: '';
    top: 50px;
    left: 50%;
    margin-left: -10px;
    width: 20px;
    height: 2px;
    background: #8970ff;
  }
</style>