<template>
  <h1>{{ count }}</h1>
  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>

  <div class="task-template">
    <div style="display: flex; flex-direction: row">
      <input v-model="gyoumu_title" placeholder="業務名" />
      <input
        v-model="view_task_time"
        placeholder="作業時間"
        v-on:change="on_change_task_time"
      />
      {{ task_rate }}%
    </div>
    <textarea v-model="message" placeholder="メモ"></textarea>
  </div>
</template>

<style>
.task-template {
  display: flex;
  flex-direction: column;
}
</style>

<script setup lang="ts">
import { computed, ref } from 'vue'

const count = ref(0)

const gyoumu_title = ref<string>('')
const task_time = ref('')
let view_task_time: string = ''
let editing_task_time: string = ''
const task_rate = ref(0)

const on_change_task_time = () => {
  view_task_time = view_task_time + 'h'
}

const message = ref<string>('')

const increment = () => {
  count.value++
}

const decrement = () => {
  count.value--
}
</script>
