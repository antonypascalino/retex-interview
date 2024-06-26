<script setup>

import IconRightArrow from "@/components/icons/IconRightArrow.vue";
</script>

<template>
  <div class="support-banner">
    <h1>Il tuo supporto è fondamentale</h1>
    <div class="contribute">
      <p>Dai il tuo contributo</p>
      <IconRightArrow color="black" />
    </div>
  </div>
</template>

<style scoped>

.support-banner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #F4F1DE;
  padding: 60px 40px;
}

.contribute {
  display: flex;
  cursor: pointer;
  gap: 10px;
  font-weight: bold;
}

h1 {
  font-size: 2.5rem;
  font-weight: bold;
}


</style>