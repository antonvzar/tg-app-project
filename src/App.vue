<template>
  <div class="app">
    <Header />
    <main class="main">
      <RouterView />
    </main>
    <nav class="bottom-nav">
      <RouterLink to="/" class="nav-link">Главная</RouterLink>
      <RouterLink to="/research" class="nav-link">Исследования</RouterLink>
      <RouterLink to="/ph-meter" class="nav-link">PH-метр</RouterLink>
      <RouterLink to="/article-analysis" class="nav-link">Анализ статей</RouterLink>
    </nav>
  </div>
</template>

<script setup>
import { RouterView } from 'vue-router'
import Header from '@/components/Header.vue'
</script>

<style>
:root {
  --persian-blue: #1c39bb;
  --dark-ultramarine: #1e2460;
  --royal-blue: #2b4bde;
  --frost-blue: #4682b4;
  --deep-sky: #00688b;
  --amethyst: #9966cc;
  --deep-purple: #483d8b;
  --header-height: 48px;
  --bottom-nav-height: 48px;
}

html,
body {
  margin: 0;
  padding: 0;
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  background: linear-gradient(
    45deg,
    var(--persian-blue),
    var(--dark-ultramarine),
    var(--royal-blue),
    var(--deep-purple),
    var(--frost-blue),
    var(--deep-sky),
    var(--amethyst)
  );
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
  color: white;
  font-family:
    -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans',
    'Helvetica Neue', sans-serif;
}

* {
  color: white;
}

.app {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.app-container {
  width: 100%;
  height: 100%;
  position: relative;
  background: linear-gradient(
    45deg,
    var(--persian-blue),
    var(--dark-ultramarine),
    var(--royal-blue),
    var(--deep-purple),
    var(--frost-blue),
    var(--deep-sky),
    var(--amethyst)
  );
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
  display: flex;
  flex-direction: column;
}

@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.main {
  flex: 1;
  padding-top: var(--header-height);
  padding-bottom: var(--bottom-nav-height);
  overflow-y: auto;
  -webkit-overflow-scrolling: touch;
}

.bottom-nav {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: var(--bottom-nav-height);
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 0 16px;
  background: rgba(90, 132, 166, 0.38);
  backdrop-filter: blur(90.51px);
}

.nav-link {
  color: white;
  text-decoration: none;
  font-size: 12px;
  opacity: 0.8;
  transition: opacity 0.3s ease;
}

.nav-link:hover,
.nav-link.router-link-active {
  opacity: 1;
}

@media screen and (min-width: 390px) {
  .app-container {
    width: 390px;
    height: 844px;
    border-radius: 32px;
    overflow: hidden;
  }

  .nav-link {
    font-size: 14px;
  }
}

/* Scrollbar styling */
::-webkit-scrollbar {
  width: 4px;
}

::-webkit-scrollbar-track {
  background: rgba(255, 255, 255, 0.1);
}

::-webkit-scrollbar-thumb {
  background: rgba(255, 255, 255, 0.3);
  border-radius: 2px;
}

::-webkit-scrollbar-thumb:hover {
  background: rgba(255, 255, 255, 0.5);
}
</style>
