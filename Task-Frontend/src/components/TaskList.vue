<script setup lang="ts">
import { ref } from 'vue'

// 1. Passe diese Felder exakt an die Attribute in deiner Task.java an
interface Task {
  id: number
  title: string
  deadline: string // Neues Feld für die Deadline
  completed: boolean
}

// 2. Beispiel-Entitäten mit Deadline-Datum
const tasks = ref<Task[]>([
  { id: 1, title: 'Spring Boot Backend testen (M1)', deadline: '2026-10-31', completed: true },
  { id: 2, title: 'Vue.js Projekt erstellen (M2)', deadline: '2026-11-05', completed: true },
  { id: 3, title: 'Eigene Komponente mit v-for rendern', deadline: '2026-11-10', completed: false }
])
</script>

<template>
  <div class="task-container">
    <h2>Meine Aufgabenliste</h2>

    <ul>
      <li v-for="task in tasks" :key="task.id">
        <div class="task-details">
          <strong>{{ task.title }}</strong>
          <span class="deadline">Fällig bis: {{ task.deadline }}</span>
        </div>
        <span class="status">{{ task.completed ? '✅' : '❌' }}</span>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.task-container {
  background-color: #2b4970;
  padding: 20px;
  border-radius: 8px;
  color: #5c1818;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  padding: 10px;
  margin-bottom: 8px;
  background: #39769f;
  border: 1px solid #c42828;
  border-radius: 4px;
  display: flex;
  justify-content: space-between;
  align-items: center;
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
