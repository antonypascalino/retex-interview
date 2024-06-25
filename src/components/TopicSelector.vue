<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  backgroundColor: String, // Prop to accept background color
});
</script>

<template>
  <Button :style="{ background: backgroundColor }">
    <h1>
      <slot name="topic"></slot>
    </h1>
  </Button>
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

</style>