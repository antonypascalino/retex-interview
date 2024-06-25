<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  backgroundColor: String, // Prop to accept background color
});
</script>

<template>
  <div class="label-container">
    <h1>
      <slot name="topic"></slot>
    </h1>
  </div>
</template>

<style scoped>

.label-container {
  padding: 2px 10px;
  font-size: 0.3rem;
  background: white;
  border: 1px solid black;
  border-radius: 5px;
  box-shadow: -2px 2px 0 0 black;
  width: fit-content;
}

</style>