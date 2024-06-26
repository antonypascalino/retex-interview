<script setup>

import TopicLabel from "@/components/TopicLabel.vue";
import CardFooter from "@/components/CardFooter.vue";

defineProps({
  image: String,
  topic: String,
  title: String,
  author: String,
  date: String,
  media: String, //Temporary solution, should have a different property for different medias elements
  showMedia: Boolean,
});
</script>

<template>
  <div class="card" :style="{ backgroundImage: `url(${image})` }">
    <div class="background-black">
      <TopicLabel>
        <template #topic>
          {{ topic }}
        </template>
      </TopicLabel>
      <div v-if=showMedia class="media">
        <img :src=media class="media-element  "/>
        {{showMedia}}
      </div>
      <h1 class="title">{{ title }}</h1>
      <CardFooter
          :author="author"
          :date="date"
      />
    </div>
  </div>
</template>

<style scoped>

.card {
  display: flex;
  justify-content: center;
  align-items: center;
  background: no-repeat center center/cover;
  width: 100%;
  height: 100vh;
}

.background-black {
  background-color: rgba(0, 0, 0, 0.4);
  display: flex;
  flex-direction: column;
  justify-content: end;
  padding: 35px;
  gap: 1.2vh;
  background-size: cover;
  background-position: center;
  width: 100%;
  height: 100%;
}

.title {
  font-size: 1.6vw;
  margin-right: 20%;
}

.media {
  display: flex;
  width: 500px;
}

.media-element   {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

p, h1 {
  color: white;
}

@media (max-width: 1050px) {
  .title {
    font-size: 1.4rem;
  }
}


</style>