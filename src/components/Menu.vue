<script setup>

import MenuItem from "@/components/MenuItem.vue";
</script>

<template>
  <div class="menu">
    <MenuItem>
      <template #title>
        Articoli
      </template>
      <template #description>
        Trend, dati e novità del Terzo Settore.
      </template>
    </MenuItem>
    <MenuItem>
      <template #title>
        Storie
      </template>
      <template #description>
        Letture ed approfondimenti dei fenomeni complessi.
      </template>
    </MenuItem>
    <MenuItem>
      <template #title>
        Interviste
      </template>
      <template #description>
        Racconti reali di persone ed organizzazioni.
      </template>
    </MenuItem>
    <MenuItem>
      <template #title>
        Opinioni
      </template>
      <template #description>
        Riflessioni e confronti dei nostri opinionisti.
      </template>
    </MenuItem>
    <MenuItem>
      <template #title>
        Podcast
      </template>
      <template #description>
        Un luogo per dare voce ai protagonisti della sostenibilità.
      </template>
    </MenuItem>
    <MenuItem>
      <template #title>
        Bookazine
      </template>
      <template #description>
        Una rivista da leggere e un libro da conservare.
      </template>
    </MenuItem>
  </div>
  <div class="bottom-menu">
    <p class="bottom-menu-item">Chi siamo</p>
    <p class="bottom-menu-item">Comitato editoriale</p>
    <p class="bottom-menu-item">Servizi</p>
    <p class="bottom-menu-item">Agenda/Eventi</p>
    <p class="bottom-menu-item">Mappa dell'attivismo</p>
    <p class="bottom-menu-item">Inchieste crowdfunding</p>
  </div>
</template>

<style scoped>

.menu {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

.bottom-menu {
  display: flex;
}

.bottom-menu-item {
  border: 0.9px solid black;
  padding: 30px;
  flex: 1;
  text-align: center;
  font-size: 1.2rem;
  cursor: pointer;
}

</style>