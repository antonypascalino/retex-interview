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
  hasBackground: Boolean,
  showMedia: Boolean
});
</script>

<template>
  <div class="card" :style="{
      background: hasBackground ? `url(${image})` : 'white',
      backgroundSize: 'cover',
      backgroundPosition: 'center'
  }">
    <div class="background-black">
      <TopicLabel>
        <template #topic>
          {{ topic }}
        </template>
      </TopicLabel>
      <div v-if="media" class="media">
        <img :src=media class="media-element  "/>
      </div>
      <h1 class="title"
          :style="{ color: hasBackground ? 'white' : 'black',
      }">
        {{ title }}
      </h1>
      <CardFooter :style="{ color: hasBackground ? 'white' : 'black' }"
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
  width: 100%;
  height: 100vh;
  border-bottom: 1px solid black;
}

.background-black {
  display: flex;
  flex-direction: column;
  justify-content: end;
  padding: 35px;
  gap: 20px;
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
  border: 1px solid lightgrey;
  border-radius: 5px;
  justify-content: center;
  flex-grow: 1;
}

.media-element   {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

p, h1 {
  color: black;
}

@media (max-width: 1050px) {
  .title {
    font-size: 1.4rem;
  }

  .media {
    margin-left: calc(25% - 70px);
  }
}

</style>