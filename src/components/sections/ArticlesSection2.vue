<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue';
import BackgroundCard from "@/components/BackgroundCard.vue";
import NoBackgroundCard from "@/components/NoBackgroundCard.vue";

const articles = ref([
  {
    image: 'src/assets/Odessa.png',
    topic: 'PROGETTO ARCA',
    title: '“Qui Odessa”, fotografie, progetti e solidarietà',
    author: 'Redazione',
    date: '13 Luglio 2022',
    media: '',
    hasBackground: true,
    showMedia: false
  },
  {
    image: 'src/assets/Violenza.jpeg',
    topic: 'ADOLESCENTI',
    title: 'Storie fra ragazzi permeate di violenza. A Napoli 12enne sfregiata da 17enne',
    author: 'Luca Cereda',
    date: '13 Luglio 2022',
    media: '',
    hasBackground: true,
    showMedia: false
  },
  {
    image: 'src/assets/Cooperativa.jpeg',
    topic: 'ECONOMIA CIVILE',
    title: '“Co-agitiamo”, Tiggiano una cooperativa di comunità contro lo spopolamento',
    author: 'Emiliano Moccia',
    date: '12 Luglio 2022',
    media: '',
    hasBackground: false,
    showMedia: false
  },
  {
    image: 'src/assets/Abusi.jpeg',
    topic: 'SPORT',
    title: 'Troppi abusi nello sport minorile, il governo interviene',
    author: 'Diletta Grella',
    date: '7 Luglio 2022',
    media: 'src/assets/podcast.png',
    hasBackground: false,
    showMedia: false
  },
  {
    image: 'src/assets/Donne.jpeg',
    topic: 'SOCIETÀ',
    title: 'Donne e nuove generazioni: con loro riparte l’Italia',
    author: 'Anna Spena',
    date: '7 Luglio 2022',
    media: 'src/assets/Donne.jpeg',
    hasBackground: false,
    showMedia: false
  }
]);

const screenWidth = ref(window.innerWidth);
const isMobile = ref(screenWidth.value <= 1050);

const handleResize = () => {
  screenWidth.value = window.innerWidth;
  isMobile.value = screenWidth.value <= 1050;
};

onMounted(() => {
  window.addEventListener('resize', handleResize);
});

onBeforeUnmount(() => {
  window.removeEventListener('resize', handleResize);
});

const getClass = (index) => {
  switch (index) {
    case 0:
      return 'article-main';
    case 1:
      return 'article-secondary';
    case 2:
      return 'article-tertiary';
    case 3:
      return 'article-quaternary';
    case 4:
      return 'article-fifth';
    default:
      return '';
  }
};

</script>

<template>
  <div class="grid-container">
    <component
        v-for="(article, index) in articles"
        :is="isMobile ? NoBackgroundCard : BackgroundCard"
        :key="index"
        :class="getClass(index)"
        :media="article.media"
        :image="article.image"
        :topic="article.topic"
        :title="article.title"
        :author="article.author"
        :date="article.date"
        :hasBackground="article.hasBackground"
        :showMedia="article.showMedia"
    />
  </div>
</template>

<style scoped>
.grid-container {
  display: grid;
  grid-template-areas:
    "main secondary tertiary"
    "quaternary fifth fifth";
  gap: 1.5px;
}

.article-main {
  grid-area: main;
  height: 520px;
  width: calc(100vw/3);
}

.article-secondary {
  grid-area: secondary;
  height: 520px;
  width: calc(100vw/3);
}

.article-tertiary {
  grid-area: tertiary;
  height: 520px;
  width: calc(100vw/3);
}

.article-quaternary {
  grid-area: quaternary;
  height: 520px;
  width: calc(100vw/3);
}

.article-fifth {
  grid-area: fifth;
  height: 520px;
  width: calc(100vw*2/3);
}

@media (max-width: 1050px) {
  .grid-container {
    grid-template-areas:
      "main"
      "secondary"
      "tertiary"
      "quaternary"
      "fifth";
    grid-template-columns: 1fr;
  }

  .article-main, .article-secondary, .article-tertiary, .article-quaternary, .article-fifth {
    height: auto;
    width: auto;
  }
}
</style>
