<template>
  <div>
    <h1>{{ state.count }}, doubled={{ state.double }}</h1>
    <button @click="UpdateCount(true)">PLUS</button>
    <button @click="UpdateCount(false)">MINUS</button>
    <button @click="UpdateCount(false)">MINUS</button>
  </div>
</template>
<script>
import { reactive, computed } from "vue";

export default {
  setup() {
    const state = reactive({
      count: 0,
      double: computed(() => state.count * 2),
    });

    function UpdateCount(increment) {
      if (increment) state.count++;
      else state.count--;
    }
    return { state, UpdateCount };
  },
};
</script>

<style></style>
