<script setup>

import BlogArticle from "@/components/BlogArticle.vue";
import IconRightArrow from "@/components/icons/IconRightArrow.vue";
</script>

<template>
  <div class="blog-banner">
    <div class="blog-logo">
      <p class="logo">Il Blog</p>
    </div>
    <div class="blog-article">
      <BlogArticle
          authorImage="src/assets/authors/BlogAuthor.jpeg"
          author="Paolo dell'Oca"
          title="Il Becco dell'oca"
      />
    </div>
    <div class="blog-article">
      <BlogArticle
          authorImage="src/assets/authors/BlogAuthor.jpeg"
          author="Pasquale Pugliese"
          title="Disarmato"
      />
    </div>
    <div class="blog-article">
      <BlogArticle
          authorImage="src/assets/authors/BlogAuthor.jpeg"
          author="Lorenzo Maria Alvaro"
          title="Battiperminuto"
      />
    </div>
    <div class="blog-article">
      <BlogArticle
          authorImage="src/assets/authors/BlogAuthor.jpeg"
          author="Elena Zanella"
          title="La Zanzarella"
      />
    </div>
    <div class="blog-article">
      <BlogArticle
          authorImage="src/assets/authors/BlogAuthor.jpeg"
          author="Laura Orestano"
          title="Impact Q&A"
      />
    </div>
    <div class="all-blogs">
      <h1 class="blogs">Tutti i blog</h1>
      <IconRightArrow color="black"/>
    </div>
  </div>
</template>

<style scoped>

.blog-logo {
  flex: 1 0;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 0.5px solid black;
}

.logo {
  color: #E63036;
  font-size: 2rem;
  font-weight: 800;
}

.blog-banner {
  display: flex;
  width: 100vw;
  flex-wrap: wrap;
}

.blog-article {
  flex: 1 0;
}

.all-blogs {
  display: none
}

@media (max-width: 1050px) {
  .blog-article {
    flex: 1 0 50%;
  }

  .blog-logo {
    flex: 1 0 50%;
  }

  .blog-article:nth-child(n+6):not(.blog-logo, .all-blogs) {
    display: none;
  }

  .all-blogs {
    display: flex;
    flex-direction: column;
    flex: 1 0 50%;
    border: 0.5px solid black;
    justify-content: center;
    align-items: center;
  }
}

</style>