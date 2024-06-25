<script setup>
import IconRightArrow from "@/components/icons/IconRightArrow.vue";

  defineProps({
  src: String
});
</script>

<template>
  <div class="card-footer">
    <div class="author-picture">
      <img :src=getAuthorImage(author) alt="author" class="author-image"/>
    </div>
    <p>Di {{ author }}</p>
    <p>{{ date }}</p>
    <button class="arrow">
      <IconRightArrow/>
    </button>
  </div>
</template>

<style scoped>

</style>