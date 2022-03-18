<template>
  <div class="task-template">
    <div style="display: flex; flex-direction: row">
      <input v-model="task_title" placeholder="業務名" />
      <input
        v-model="view_task_time"
        placeholder="作業時間"
        @focus="on_focus"
        @blur="on_blur"
      />
      {{ task_rate }}%
    </div>
    <textarea v-model="task_note" placeholder="メモ"></textarea>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
  task_title: String,
  task_time: Number,
  task_rate: Number,
  task_note: String,
})

const view_task_time = ref('')

// クリックされた時、最後尾にhがあれば、hを消す
// もしhがない場合、何もしない。
const on_focus = () => {
  if (view_task_time.value.slice(-1) == 'h') {
    view_task_time.value = view_task_time.value.slice(0, -1)
  }
}

// フォーカスが外れた時、最後にhがなければ、hを追加する
// もしhがあった場合、何もしない。
const on_blur = () => {
  if (view_task_time.value == '') {
    return
  }
  if (view_task_time.value.slice(-1) != 'h') {
    view_task_time.value = view_task_time.value + 'h'
  }
}
</script>
