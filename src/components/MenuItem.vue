<script setup>

</script>

<template>
  <div class="menu-item">
    <h1>
      <slot name="title"></slot>
    </h1>
    <p>
      <slot name="description"></slot>
    </p>
  </div>
</template>

<style scoped>

.menu-item {
  border: 0.9px solid black;
  height: 300px;
  display: flex;
  flex-direction: column;
  justify-content: end;
  padding: 25px;
  font-size: 1.6rem;
  cursor: pointer;
}

p {
  font-size: 1.2rem;
}

</style>