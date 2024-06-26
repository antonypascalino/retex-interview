<script setup>

</script>

<template>
  <footer>
    <ul class="links">
      <li>
        <a href="#">Il Gruppo</a>
      </li>
      <li>
        <a href="#">Note Legali</a>
      </li>
      <li>
        <a href="#">Chi Siamo</a>
      </li>
      <li>
        <a href="#">Condizioni d'uso</a>
      </li>
      <li>
        <a href="#">Privacy</a>
      </li>
      <li>
        <a href="#">Scrivici</a>
      </li>
      <li>
        <a href="#">Pubblicità</a>
      </li>
    </ul>
    <p>© 1994-2022 Vita Società Editoriale S.p.A.</p>
  </footer>
</template>

<style scoped>

footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: transparent;
  height: 100px;
  padding: 40px;
}

.links {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
  list-style: none;
  padding: 0;
}

@media (max-width: 1050px) {
  footer, .links {
    flex-direction: column;
    align-items: start;
    padding: 20px;
  }
}

</style>