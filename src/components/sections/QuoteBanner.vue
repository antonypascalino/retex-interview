<script setup>

import IconRightArrow from "@/components/icons/IconRightArrow.vue";
</script>

<template>
  <div class="banner">
    <h1>Essere troppo seri non è cosa molto seria</h1>
    <div class="cit">
      <p>[Detto africano]</p>
    </div>
  </div>
</template>

<style scoped>

.banner {
  display: flex;
  flex-direction: column;
  padding: 60px 140px;
  background: url("../../assets/Quote.png") no-repeat center center/cover;
  color: white;
  font-size: 1.5rem;

}

.cit {
  font-style: italic;
}

@media (max-width: 1050px) {
  .banner {
    padding: 60px 40px;
    font-size: 3vw;
  }
}


</style>