
<script setup lang="ts">

import TaskList from './components/TaskList.vue'
</script>

<template>
  <main class="app-main">
    <h1>TasksApp</h1>


    <TaskList />
  </main>
</template>

<style scoped>
.app-main {
  max-width: 600px;
  margin: 0 auto;
  padding: 2rem;
  font-family: Arial, sans-serif;
}
</style>
