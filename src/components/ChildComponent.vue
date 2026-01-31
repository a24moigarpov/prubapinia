<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <h3 class="green">{{ msg }}</h3>
    <p>
      I am a child component receiving data from my parent!
    </p>
  </div>
</template>

<style scoped>
h3 {
  font-weight: 500;
  font-size: 1.2rem;
  top: -10px;
}

.greetings h3,
.greetings p {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h3,
  .greetings p {
    text-align: left;
  }
}
</style>
