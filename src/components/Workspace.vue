<script setup lang="ts">
  import Header from './Header.vue';
  import { ref } from 'vue';

  const statusName = ref('')
  const statuses = ref([{ name: 'First chat' }])

  function submit() {
    statuses.value.push({name: statusName.value});
    statusName.value = ''
  }
</script>

<template>
  <div class="workspace">
    <Header />

    <div class="statuses">
      <ul class="statuses__list">
        <li v-for="status in statuses">
          {{ status.name }}
        </li>
      </ul>
      <form class="statuses__form" @submit.prevent="submit">
        <input class="statuses__input" type="text" v-model="statusName">
        <button class="statuses__add" type="submit" title="Add new status">
          <svg class="svg-icon" viewBox="0 0 20 20">
							<path d="M14.613,10c0,0.23-0.188,0.419-0.419,0.419H10.42v3.774c0,0.23-0.189,0.42-0.42,0.42s-0.419-0.189-0.419-0.42v-3.774H5.806c-0.23,0-0.419-0.189-0.419-0.419s0.189-0.419,0.419-0.419h3.775V5.806c0-0.23,0.189-0.419,0.419-0.419s0.42,0.189,0.42,0.419v3.775h3.774C14.425,9.581,14.613,9.77,14.613,10 M17.969,10c0,4.401-3.567,7.969-7.969,7.969c-4.402,0-7.969-3.567-7.969-7.969c0-4.402,3.567-7.969,7.969-7.969C14.401,2.031,17.969,5.598,17.969,10 M17.13,10c0-3.932-3.198-7.13-7.13-7.13S2.87,6.068,2.87,10c0,3.933,3.198,7.13,7.13,7.13S17.13,13.933,17.13,10"></path>
						</svg>
        </button>
      </form>
      
    </div>
  </div>
</template>

<style scoped>
  .workspace {
    width: 100%;
    padding: 50px;
  }

  .statuses {
    display: flex;
    align-items: center;
    margin: 50px 0 0;
  }

  .statuses__list {
    display: flex;
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .statuses__list li {
    width: 100px;
    padding: .3rem 1rem .3rem 0;
    text-overflow: ellipsis;
    overflow: hidden; 
    white-space: nowrap;
  }

  .statuses__add {
    background: transparent;
    border: none;
    box-shadow: none;
  }

  .statuses__form {
    display: flex;
    align-items: flex-start;
  }

  .statuses__input {
    background: transparent;
    line-height: 2rem;
    border-top: none;
    border-bottom: 1px solid #8970ff;
    border-left: none;
    border-right: none;
    box-shadow: none;
  }

  .svg-icon {
    width: 2rem;
    height: 2rem;
  }

  .svg-icon path,
  .svg-icon polygon,
  .svg-icon rect {
    fill: #8970ff;
  }

  .svg-icon circle {
    stroke: #8970ff;
  }
</style>