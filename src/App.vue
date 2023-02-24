<script setup lang="ts">
import { ref } from 'vue'

const text = ref('')
const url = ref('')

const handleImageChange = async () => {
  if (text.value.length < 1) return
  url.value = text.value
}

</script>

<template>
  <main>
    <div class="wrapper">
      <input v-model="text">
      <button @click="handleImageChange">Send Request</button>
      <img :src="`https://robohash.org/${url}.png`">
    </div>
  </main>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  max-width: 25rem;
  margin: 0 auto;
}

input {
  display: block;
  padding: 0.5rem;
  margin-bottom: 1.25rem;
}

button {
  padding: 0.625rem 1rem;
  width: 100%;
  border-radius: 0.75rem;
}
</style>
