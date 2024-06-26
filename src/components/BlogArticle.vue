<script setup>

const props = defineProps({
  authorImage: String,
  author: String,
  title: String,
});

</script>

<template>
  <div class="blog-article">
    <img class=author-image :src=authorImage alt=" image" />
    <h1>{{ title }}</h1>
    <p>Di {{ author }}</p>
  </div>
</template>

<style scoped>

.blog-article {
  display: flex;
  flex-direction: column;
  gap: 10px;
  justify-content: center;
  align-items: center;
  border: 0.5px solid black;
  padding: 20px;
  height: 200px;
  cursor: pointer;
}

.author-image {
  width: 50px;
  height: 50px;
  border-radius: 50%;
}

h1 {
  font-size: 1.2rem;
  text-align: center;
}

p {
  font-size: 0.8rem;
}

</style>