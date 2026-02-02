<script setup>
import { useCounterStore } from "../stores/counter";

const store = useCounterStore();
</script>

<template>
  <div class="about">
    <h1>About Page (Pinia Read)</h1>
    <div class="card">
      <h2>Retrieving Data from Pinia</h2>
      <p>This data persists across route navigation.</p>

      <p>
        Name: <strong>{{ store.name }}</strong>
      </p>
      <p>
        Count: <strong>{{ store.count }}</strong>
      </p>
      <p>
        Double Count (Getter): <strong>{{ store.doubleCount }}</strong>
      </p>
    </div>
  </div>
</template>

<style>
.about {
  padding: 20px;
}
.card {
  padding: 20px;
  border: 1px solid #eee;
}
</style>
