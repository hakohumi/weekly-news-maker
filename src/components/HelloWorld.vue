<template>
  <TaskInputter
    :task_title="task_title"
    :task_time="task_time"
    :task_rate="task_rate"
    :task_note="task_note"
  />
</template>

<style>
.task-template {
  display: flex;
  flex-direction: column;
}
</style>

<script setup lang="ts">
import { ref } from 'vue'
import TaskInputter from './TaskInputter.vue'

const task_title = ref<string>('')
const task_time = ref<number>(0)
const task_rate = ref<number>(0)

const task_note = ref<string>('')
</script>
