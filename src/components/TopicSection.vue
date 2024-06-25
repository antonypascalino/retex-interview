<script setup>
import TopicSelector from "@/components/TopicSelector.vue";
</script>

<template>
  <div class="topic-section">
    <h1 class="title">Tutti i temi</h1>
    <ul class="topics">
      <li>
        <TopicSelector backgroundColor="#E2F1E8">
          <template #topic>
            AMBIENTE
          </template>
        </TopicSelector>
      </li>
      <li>
        <TopicSelector>
          <template #topic>
            ECONOMIA
          </template>
        </TopicSelector>
      </li>
      <li>
        <TopicSelector backgroundColor="#F1DADA">
          <template #topic>
            MONDO
          </template>
        </TopicSelector>
      </li>
      <li>
        <TopicSelector >
          <template #topic>
            NON PROFIT
          </template>
        </TopicSelector>
      </li>
      <li>
        <TopicSelector backgroundColor="#F1F1E2">
          <template #topic>
            POLITICA
          </template>
        </TopicSelector>
      </li>
      <li>
        <TopicSelector>
          <template #topic>
            SOCIETÁ
          </template>
        </TopicSelector>
      </li>
      <li>
        <TopicSelector>
          <template #topic>
            WELFARE
          </template>
        </TopicSelector>
      </li>
    </ul>
  </div>
</template>

<style scoped>

.topic-section {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 40px 30px;
}

.topics {
  display: flex;
  gap: 20px;
  list-style: none;
}

.title {
  font-size: 3.5rem;
  font-weight: bold;
}

@media (max-width: 1050px) {
  .topic-section {
    flex-direction: column;
    justify-content: left;
    align-items: start;
    padding: 0 30px;
  }

  .topics {
    padding-left: 0;
  }
}

</style>