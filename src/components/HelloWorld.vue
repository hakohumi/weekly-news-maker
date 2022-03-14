<template>
  <h1>{{ count }}</h1>
  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>

  <div class="input-area">
    {{ message }}
    <textarea v-model="message" placeholder="add multiple lines"></textarea>
  </div>
</template>

<style>
.input-area {
  display: flex;
  flex-direction: column;
}
</style>

<script setup lang="ts">
import { ref } from 'vue'

const count = ref(0)

const message = ref<string>(' ')

const increment = () => {
  count.value++
}

const decrement = () => {
  count.value--
}
</script>
