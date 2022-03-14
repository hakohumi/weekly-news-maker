<template>
  <h1>{{ count }}</h1>
  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const count = ref(0);

    const increment = () => {
      count.value++;
    };

    const decrement = () => {
      count.value--;
    };
    return {
      count,
      increment,
      decrement,
    };
  },
});
</script>