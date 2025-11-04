<script setup>
import { ref, computed } from 'vue'

const weightKg = ref(0)

const weightLbs = computed(() => {
  return (weightKg.value * 2.20462262).toFixed(2)
})
</script>

<template>
  <div class="container">
    <h1>Конвертер веса</h1>

    <div class="input-group">
      <label for="weight">Введите вес (кг):</label>
      <input
        id="weight"
        type="number"
        v-model.number="weightKg"
        min="0"
        step="0.1"
      />
    </div>

    <table>
      <thead>
        <tr>
          <th>Метрическая система</th>
          <th>Британская система</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>{{ weightKg }} кг</td>
          <td>{{ weightLbs }} фунтов (lbs)</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
.container {
  max-width: 600px;
  margin: 2rem auto;
  padding: 2rem;
  font-family: Arial, sans-serif;
}

h1 {
  color: #42b983;
  text-align: center;
}

.input-group {
  margin: 2rem 0;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

label {
  font-weight: bold;
  color: #2c3e50;
}

input {
  padding: 0.5rem;
  font-size: 1rem;
  border: 2px solid #42b983;
  border-radius: 4px;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 2rem;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

th, td {
  padding: 1rem;
  text-align: left;
  border: 1px solid #ddd;
}

th {
  background-color: #42b983;
  color: white;
  font-weight: bold;
}

tr:nth-child(even) {
  background-color: #f9f9f9;
}

tr:hover {
  background-color: #f0f0f0;
}
</style>
