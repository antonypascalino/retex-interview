<script setup>
import IconRightArrow from "@/components/icons/IconRightArrow.vue";

  defineProps({
  author: String,
    date: String,
});

const authorImages = {
  'Alessandro Puglia': 'src/assets/authors/Alessandro_Puglia.jpeg',
  'Ugo Lombi': 'src/assets/authors/Ugo_Lombi.png',
  'Diletta Grella': 'src/assets/authors/Diletta_Grella.jpeg',
  'Anna Spena': 'src/assets/authors/Anna_Spena.jpeg',
  'Luca Cereda': 'src/assets/authors/Luca_Cereda.jpeg',
  'Emiliano Moccia': 'src/assets/authors/Emiliano_Moccia.jpeg',
  'Redazione': 'src/assets/authors/Redazione.png'
}

const getAuthorImage = (authorName) => {
  return authorImages[authorName] || 'default-author-image.jpeg';
};

</script>

<template>
  <div class="card-footer">
    <div class="author-picture">
      <img :src=getAuthorImage(author) alt="author" class="author-image"/>
    </div>
    <div class="information">
      <p>Di {{ author }}</p>
      <p>{{ date }}</p>
    </div>
    <button class="arrow">
      <IconRightArrow/>
    </button>
  </div>
</template>

<style scoped>

.card-footer {
  display: flex;
  flex-direction: column;
  font-size: 0.9em;
  gap: 1.5vh;
  color: white;
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


@media (max-width: 1050px) {
  .arrow {
    display: none;
  }

  .card-footer {
    display: flex;
    flex-direction: row;
  }
}

</style>