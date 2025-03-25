<template>
  <header class="header">
    <RouterLink to="/" class="logo">
      <img src="@/components/icons/main-page-icon.svg" alt="Home" />
    </RouterLink>

    <div class="controls">
      <button @click="toggleLanguage" class="lang-toggle">
        <img
          :src="
            isRussian
              ? '/src/components/icons/Property-1-Default.svg'
              : '/src/components/icons/Property-1-Variant2.svg'
          "
          :alt="isRussian ? 'RU' : 'EN'"
        />
      </button>
      <RouterLink to="/auth" class="auth-button">
        <img src="@/components/icons/solar_exit-linear.svg" alt="Login" />
      </RouterLink>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'
import { RouterLink } from 'vue-router'

const isRussian = ref(true)

const toggleLanguage = () => {
  isRussian.value = !isRussian.value
}
</script>

<style scoped>
.header {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: var(--header-height);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 16px;
  background: rgba(90, 132, 166, 0.38);
  backdrop-filter: blur(90.51px);
  z-index: 10;
}

.logo {
  display: flex;
  align-items: center;
}

.logo img {
  height: 36px;
  width: auto;
}

.controls {
  display: flex;
  gap: 12px;
  align-items: center;
}

.lang-toggle,
.auth-button {
  display: flex;
  align-items: center;
  justify-content: center;
  background: none;
  border: none;
  padding: 8px;
  cursor: pointer;
  transition: opacity 0.3s ease;
}

.lang-toggle:hover,
.auth-button:hover {
  opacity: 0.8;
}

.lang-toggle img,
.auth-button img {
  height: 24px;
  width: auto;
}

@media screen and (min-width: 390px) {
  /* .header {
    border-top-left-radius: 20px;
    border-top-right-radius: 20px;
  } */
}
</style>
