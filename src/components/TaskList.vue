<script setup lang="ts">
import { ref } from 'vue'

interface Task {
  id: number
  title: string
  deadline: string
  completed: boolean
}

const tasks = ref<Task[]>([
  { id: 1, title: 'Spring Boot Backend testen (M1)', deadline: '2026-10-31', completed: true },
  { id: 2, title: 'Vue.js Projekt erstellen (M2)', deadline: '2026-11-09', completed: true },
  { id: 3, title: '(M3) Aufgabe erstellen', deadline: '2026-11-14', completed: false },
  { id: 4, title: 'laptop reparieren lassen', deadline: '2026-11-17', completed: false }
])
</script>

<template>
  <div class="task-container">
    <h2>Aufgabenliste</h2>

    <ul>
      <li
        v-for="task in tasks"
        :key="task.id"
        :style="{
          borderColor: task.completed ? '#28a745' : '#dc3545',
          backgroundColor: task.completed ? '#ecd9ce' : '#fff1ed'
        }"
      >
        <div class="task-details">
          <strong>{{ task.title }}</strong>
          <span class="deadline">Fällig bis: {{ task.deadline }}</span>
        </div>
        <span class="status">{{ task.completed ? '✅' : '❌' }}</span>
      </li>
    </ul>
  </div>
</template>

<style>
body {
  background-color: #f4ece4;
  margin: 0;
}
</style>

<style scoped>
.task-container {
  background-color: #e4c098;
  padding: 20px;
  border-radius: 8px;
  color: #5c1818;
  max-width: 500px;
  margin: 10px auto;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  padding: 12px;
  margin-bottom: 10px;
  border: 2px solid;
  border-radius: 6px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  transition: background-color 0.2s;
}
.task-details {
  display: flex;
  flex-direction: column;
}
.deadline {
  font-size: 0.85em;
  color: #666;
  margin-top: 4px;
}
.status {
  font-size: 1.2em;
}
</style>
