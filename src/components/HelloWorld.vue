<template>
  <h1>{{ count }}</h1>
  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>

  <div class="input-area">
    <input v-model="gyoumu_title" placeholder="業務名" />
    {{ gyoumu_title }}
    <textarea v-model="message" placeholder="メモ"></textarea>
    {{ message }}
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

const gyoumu_title = ref<string>('test')
const message = ref<string>('')

const increment = () => {
  count.value++
}

const decrement = () => {
  count.value--
}
</script>
