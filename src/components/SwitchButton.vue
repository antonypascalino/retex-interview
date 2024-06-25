<script setup>
import { ref } from 'vue';
import IconTextMode from "@/components/icons/IconTextMode.vue";
import IconImageMode from "@/components/icons/IconImageMode.vue";

const activeButton = ref(null);

const isActive = (button) => activeButton.value === button;

const activate = (button) => {
  activeButton.value = button;
};
</script>

<template>
  <div class="button-switch">
    <button
        :class="{ active: isActive('button1') }"
        @click="activate('button1')"
    >
      <IconTextMode/>
    </button>
    <button
        :class="{ active: isActive('button2') }"
        @click="activate('button2')"
    >
      <IconImageMode/>
    </button>
  </div>
</template>

<style scoped>
.button-switch {
  display: flex;
}

button {
  padding: 7px;
  font-size: 16px;
  cursor: pointer;
  background: transparent;
}

button.active {
  border: 1px solid black;
  border-radius: 5px;
  box-shadow: -2px 2px 0 0 black;
}

/* Different approach respect to :after */
button:not(.active) {
  border: 1px solid transparent;
  border-radius: 5px;
  box-shadow: -2px 2px 0 0 transparent;
}
</style>