
<script setup lang="ts">
// Hier importieren wir deine neue Komponente
import TaskList from './components/TaskList.vue'
</script>

<template>
  <main class="app-main">
    <h1>Task-App Frontend</h1>

    <!-- Hier binden wir die Komponente ein -->
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
