<script setup>
import Header from "@/components/Header.vue";
import TopicSection from "@/components/TopicSection.vue";
import {ref, onMounted} from 'vue';

const header = ref(null);
const content = ref(null);

onMounted(() => {
  if (header.value && content.value) {
    const headerHeight = header.value.offsetHeight;
    content.value.style.marginTop = `${headerHeight}px`;
  }
});
</script>

<template>
    <header ref="header" class="fixed-header">
      <Header />
    </header>
  <main ref="content" class="content">
    <TopicSection />
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
