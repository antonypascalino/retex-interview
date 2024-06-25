<script setup>
import Header from "@/components/Header.vue";
import TopicSection from "@/components/TopicSection.vue";
import { ref, onMounted, onBeforeUnmount } from 'vue';
import ArticlesSection1 from "@/components/ArticlesSection1.vue";

const header = ref(null);
const content = ref(null);

const adjustContentMargin = () => {
  if (header.value && content.value) {
    const headerHeight = header.value.offsetHeight;
    content.value.style.marginTop = `${headerHeight}px`;
  }
};

onMounted(() => {
  adjustContentMargin();
  window.addEventListener('resize', adjustContentMargin);
});

onBeforeUnmount(() => {
  window.removeEventListener('resize', adjustContentMargin);
});
</script>

<template>
    <header ref="header" class="fixed-header">
      <Header />
    </header>
  <main ref="content" class="content">
    <TopicSection />
    <ArticlesSection1 />
  </main>
</template>

<style scoped>

.fixed-header {
  position: fixed;
  top: 0;
  background: white;
  width: 100%;
}

TopicSection {
  position: relative;
}

</style>
