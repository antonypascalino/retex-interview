<script setup>
import { ref } from 'vue';
import ArticleCard from '../components/ArticleCard.vue';

const articles = ref([
  {
    image: 'src/assets/Lampedusa.jpeg',
    topic: 'MIGRANTI',
    title: 'Roccella Jonica, la Lampedusa che l\'Italia ignora',
    author: 'Alessandro Puglia',
    date: '29 Giugno 2022'
  },
  {
    image: 'src/assets/Ghiacciai.png',
    topic: 'ALLARMI',
    title: 'Il collasso dei ghiacciai negli scatti del fotografo ambientale Fabiano Ventura',
    author: 'Ugo Lombi',
    date: '12 Luglio 2022'
  },
  {
    image: 'src/assets/Startup.jpeg',
    topic: 'ESPERIMENTI',
    title: "Gli startupper? Li trovi al bistrot. così il DUMBO incuba relazioni",
    author: "Diletta Grella",
    date: "14 Luglio 2022",
  },
  {
    image: 'src/assets/Ucraina.png',
    topic: 'UCRAINA',
    title: "Nelle città italiane tutti in piazza per e con Kiev",
    author: "Anna Spena",
    date: "14 Luglio 2022",
  }
]);

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
  <div id="app">
    <div class="grid-container">
      <ArticleCard
          v-for="(article, index) in articles"
          :key="index"
          :class="getClass(index)"
          :image="article.image"
          :topic="article.topic"
          :title="article.title"
          :description="article.description"
          :author="article.author"
          :date="article.date"
      />
    </div>
  </div>
</template>

<style scoped>

.grid-container {
  display: grid;
  grid-template-areas:
    "main main"
    "secondary tertiary"
    "secondary quaternary";
  grid-template-columns: 2fr 1fr;
}

.article-main {
  grid-area: main;
  height: 600px;
}

.article-secondary {
  grid-area: secondary;
  height: 800px;
}

.article-tertiary {
  grid-area: tertiary;
  height: 400px;
}

.article-quaternary {
  grid-area: quaternary;
  height: 400px;
}


</style>