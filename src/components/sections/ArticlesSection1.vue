<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue';
import BackgroundCard from "@/components/BackgroundCard.vue";
import NoBackgroundCard from "@/components/NoBackgroundCard.vue";

const articles = ref([
  {
    image: 'src/assets/Lampedusa.jpeg',
    topic: 'MIGRANTI',
    title: 'Roccella Jonica, la Lampedusa che l\'Italia ignora',
    author: 'Alessandro Puglia',
    date: '29 Giugno 2022',
    media: '',
    hasBackground: true,
    showMedia: false
  },
  {
    image: 'src/assets/Ghiacciai.png',
    topic: 'ALLARMI',
    title: 'Il collasso dei ghiacciai negli scatti del fotografo ambientale Fabiano Ventura',
    author: 'Ugo Lombi',
    date: '12 Luglio 2022',
    media: 'src/assets/Ghiacciai.png',
    hasBackground: false,
    showMedia: false
  },
  {
    image: 'src/assets/Startup.jpeg',
    topic: 'ESPERIMENTI',
    title: "Gli startupper? Li trovi al bistrot. così il DUMBO incuba relazioni",
    author: "Diletta Grella",
    date: "14 Luglio 2022",
    media: 'src/assets/podcast.png',
    hasBackground: false,
    showMedia: true
  },
  {
    image: 'src/assets/Ucraina.png',
    topic: 'UCRAINA',
    title: "Nelle città italiane tutti in piazza per e con Kiev",
    author: "Anna Spena",
    date: "14 Luglio 2022",
    media: '',
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
    "main main"
    "secondary tertiary"
    "secondary quaternary";
  gap: 1.5px;
}

.article-main {
  grid-area: main;
  height: 600px;
}

.article-secondary {
  grid-area: secondary;
  height: 1000px;
}

.article-tertiary {
  grid-area: tertiary;
  height: 500px;
}

.article-quaternary {
  grid-area: quaternary;
  height: 500px;
}

@media (max-width: 1050px) {
  .grid-container {
    grid-template-areas:
      "main"
      "secondary"
      "tertiary"
      "quaternary";
    grid-template-columns: 1fr;
    margin-top: 30px;
  }

  .article-main {
    height: 400px
  }

  .article-secondary,
  .article-tertiary,
  .article-quaternary {
    height: auto
  }
}
</style>
