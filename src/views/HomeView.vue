<script setup>
import Header from "@/components/sections/Header.vue";
import TopicSection from "@/components/sections/TopicSection.vue";
import { ref, onMounted, onBeforeUnmount } from 'vue';
import ArticlesSection1 from "@/components/sections/ArticlesSection1.vue";
import SupportBanner from "@/components/sections/SupportBanner.vue";
import ArticlesSection2 from "@/components/sections/ArticlesSection2.vue";
import QuoteBanner from "@/components/sections/QuoteBanner.vue";
import BlogBanner from "@/components/sections/BlogBanner.vue";
import ArticlesSection3 from "@/components/sections/ArticlesSection3.vue";
import Footer from "@/components/sections/Footer.vue";

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
    <ArticlesSection1/>
    <SupportBanner />
    <ArticlesSection2/>
    <QuoteBanner/>
    <BlogBanner/>
    <ArticlesSection3/>
    <Footer/>
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
