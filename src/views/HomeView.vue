<script setup>
import { ref } from 'vue'
import { useCounterStore } from '../stores/counter'
import ChildComponent from '../components/ChildComponent.vue'

const store = useCounterStore()
const userInput = ref('')

function updateName() {
  store.setName(userInput.value)
  userInput.value = ''
}
</script>

<template>
  <main>
    <h1>Parent Component (Home)</h1>
    <div class="card">
      <h2>1. Component Hierarchy</h2>
      <p>Passing data to child via props:</p>
      <ChildComponent msg="Hello from Parent!" />
    </div>

    <div class="card">
      <h2>2. Pinia Storage</h2>
      <p>Current Name in Store: <strong>{{ store.name }}</strong></p>
      <div class="input-group">
        <input v-model="userInput" placeholder="Enter new name" />
        <button @click="updateName">Update Name in Pinia</button>
      </div>
      <p>Counter: {{ store.count }}</p>
      <button @click="store.increment">Increment Counter</button>
    </div>
  </main>
</template>

<style scoped>
main {
  padding: 2rem;
}
.card {
  border: 1px solid #ccc;
  padding: 1rem;
  margin-bottom: 1rem;
  border-radius: 8px;
}
.input-group {
  margin: 1rem 0;
  display: flex;
  gap: 0.5rem;
}
input {
  padding: 0.5rem;
}
button {
  padding: 0.5rem 1rem;
  cursor: pointer;
}
h1 {
  margin-bottom: 2rem;
}
</style>
