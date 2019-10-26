<template>
  <div>
    <h2>{{ state.messageOne }}</h2>
    <h2>{{ state.message }}</h2>
  </div>
</template>

<script lang="ts">
import { createComponent, reactive, ref } from "@vue/composition-api";

export default createComponent({
  setup() {
    const state = reactive<{ messageOne: string }>({
      messageOne: "Hello"
    });
    const messageTwo = ref<string>("こんにちは");

    return {
      state,
      messageTwo
    };
  }
});
</script>