<script setup>

import IconLogin from "@/components/icons/IconLogin.vue";
import SwitchButton from "@/components/SwitchButton.vue";
import IconSearch from "@/components/icons/IconSearch.vue";
</script>

<template>
  <div class="top-bar">
    <div class="top-links">
      <a href="#">Contribuisci</a>
      <a href="#">Abbonati</a>
    </div>
    <div class="login">
      <i class="login-icon">
        <IconLogin/>
      </i>
      <a href="#">Accedi</a>
    </div>
  </div>
  <div class="option-bar">
    <button @click="toggleMenu" class="option-button menu-button">
      <span v-if="!isMenuOpen">☰</span>
      <span v-else>✖</span>
    </button>
    <button class="option-button search-button">
      <IconSearch/>
    </button>
  </div>
  <div class="menu-bar">
    <nav class="main-menu" :class="{ open: isMenuOpen }">
      <ul class="menu-list">
        <li><a href="#">Tutti i temi</a></li>
        <li><a href="#">Ambiente</a></li>
        <li><a href="#">Economia</a></li>
        <li><a href="#">Mondo</a></li>
        <li><a href="#">Non Profit</a></li>
        <li><a href="#">Politica</a></li>
        <li><a href="#">Società</a></li>
        <li><a href="#">Welfare</a></li>
      </ul>
    </nav>
    <SwitchButton/>
  </div>
</template>

<style scoped>

.top-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 30px;
}

.top-links {
  display: flex;
  gap: 20px;
}

.login {
  display: flex;
  gap: 10px;
}

.option-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid black;
  border-top: 1px solid black;
  height: 96px;
}

.menu-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid black;
  padding-left: 30px;
  padding-right: 30px;
}

.option-button {
  border: none;
  background: none;
  cursor: pointer;
  height: 100%;
  width: 96px;
  font-size: 2rem;
  color: red;
}

.menu-button {
  border-right: 1px solid black;
}

.search-button {
  border-left: 1px solid black;
}


.menu-list {
  display: flex;
  gap: 25px;
  list-style: none;
  flex-direction: row;
  font-size: 1.4rem;
  padding: 0;
}

.menu-list li {
  display: flex;
  font-weight: bold;
  height: 96px;
  align-items: center;
  position: relative;
}


li::after {
  content: '';
  position: absolute;
  left: 0;
  width: 100%;
  bottom: 0;
  height: 10px;
  background-color: red;
  display: none;
}

li:hover::after {
  display: block;
}

@media (max-width: 1050px) {
  .menu-bar, .login {
    display: none;
  }

  .top-bar {
    justify-content: center;
    width: 100%;
    padding: 0;
    border-top: 1px solid black;
  }

  .top-links {
    gap: 0;
    width: 100%;
    height: 50px;
    align-items: center;
    display: flex;
  }


  .top-links > a {
    text-align: center;
    flex: 1;
    padding: 15px;
  }


  .top-links > a:first-child {
    border-right: 1px solid black;
  }

  .option-bar {
    height: 52px;
  }

  .option-button {
    width: 52px;
  }
}





</style>