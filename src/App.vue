<script setup>
import { RouterView } from 'vue-router'
import Header from './components/Header.vue'
</script>

<template>
  <div class="app">
    <div class="app-content">
      <Header />
      <main class="main">
        <RouterView />
      </main>
    </div>
  </div>
</template>

<style>
:root {
  --persian-blue: #1c39bb;
  --dark-ultramarine: #1e2460;
  --royal-blue: #2b4bde;
  --frost-blue: #4682b4;
  --deep-sky: #00688b;
  --amethyst: #9966cc;
  --deep-purple: #483d8b;
  --header-height: 60px;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  height: 100%;
  width: 100%;
  overflow: hidden;
}

body {
  font-family:
    -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans',
    'Helvetica Neue', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: white;
  background: #1e2460;
}

.app {
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

.app-content {
  width: 100%;
  height: 100%;
  max-width: 390px;
  max-height: 844px;
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
  overflow: hidden;
}

.main {
  flex: 1;
  padding: 16px;
  overflow-y: auto;
  position: relative;
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

@media screen and (min-width: 390px) {
  .app-content {
    border-radius: 20px;
  }
}
</style>
