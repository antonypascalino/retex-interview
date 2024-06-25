<script setup>
import TopicLabel from "@/components/TopicLabel.vue";
import IconRightArrow from "@/components/icons/IconRightArrow.vue";

defineProps({
  image: String,
  topic: String,
  title: String,
  description: String,
  author: String,
  date: String
});

const authorImages = {
  'Alessandro Puglia': 'src/assets/authors/Alessandro_Puglia.jpeg',
  'Ugo Lombi': 'src/assets/authors/Ugo_Lombi.png',
  'Diletta Grella': 'src/assets/authors/Diletta_Grella.jpeg',
  'Anna Spena': 'src/assets/authors/Anna_Spena.jpeg',
}

const getAuthorImage = (authorName) => {
  return authorImages[authorName] || 'default-author-image.jpeg';
};

</script>


<template>
    <div class="card" :style="{ backgroundImage: `url(${image})` }">
  <div class="background-black">
      <TopicLabel>
        <template #topic>
          {{ topic }}
        </template>
      </TopicLabel>
      <h1 class="title">{{ title }}</h1>
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
    </div>
  </div>
</template>


<style scoped>

.background-black {
  background-color: rgba(0, 0, 0, 0.4);
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

.card {
  display: flex;
  justify-content: center;
  align-items: center;
  background: red no-repeat center center/cover;
  width: 100%;
  height: 100vh;
}

p, h1 {
  color: white;
}

.title {
  font-size: 1.6rem;
  margin-right: 20%;
}

.card-footer {
  display: flex;
  flex-direction: column;
  font-size: 0.9em;
  gap: 20px;
}

.author-picture {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  overflow: hidden;
}

.author-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
}

.arrow {
  background: none;
  border: none;
  cursor: pointer;
  width: fit-content;
}
</style>