<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  backgroundColor: String, // Prop to accept background color
});
</script>

<template>
  <button :style="{ background: backgroundColor }">
    <h1>
      <slot name="topic"></slot>
    </h1>
  </button>
</template>

<style scoped>

button {
  padding: 14px;
  font-size: 0.3rem;
  cursor: pointer;
  background: white;
  border: 1px solid black;
  border-radius: 5px;
  box-shadow: -2px 2px 0 0 black;
}

@media (max-width: 1050px) {
  button {
    background: white;
  }
}

</style>