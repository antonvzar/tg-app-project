<template>
  <div class="home">
    <div class="cards-1">
      <RouterLink to="/research" class="card">
        <div class="card-icon">
          <img src="@/components/icons/homeicon2-Photoroom-research.svg" alt="Исследования" />
        </div>
        <h2>ИССЛЕДОВАНИЯ</h2>
        <p>Съешь еще этих мягких французских булок, да выпей чаю.</p>
      </RouterLink>

      <RouterLink to="/ph-meter" class="card">
        <div class="card-icon">
          <img src="@/components/icons/homeicon2-Photoroom-phmeter.svg" alt="PH-метр" />
        </div>
        <h2>PH-МЕТР</h2>
        <p>Съешь еще этих мягких французских булок, да выпей чаю.</p>
      </RouterLink>
    </div>

    <h1 class="title">КРИОПРОТЕКТОРЫ</h1>

    <div class="cards-2">
      <RouterLink to="/article-analysis" class="card">
        <div class="card-icon">
          <img src="@/components/icons/homeicon2-Photoroom-analysis.svg" alt="Анализ статей" />
        </div>
        <h2>АНАЛИЗ СТАТЕЙ</h2>
        <p>Съешь еще этих мягких французских булок, да выпей чаю.</p>
      </RouterLink>

      <RouterLink to="/contacts" class="card">
        <div class="card-icon">
          <img src="@/components/icons/homeicon2-Photoroom-1.svg" alt="Контакты" />
        </div>
        <h2>КОНТАКТЫ</h2>
        <p>Съешь еще этих мягких французских булок, да выпей чаю.</p>
      </RouterLink>
    </div>
  </div>
</template>

<script setup>
import { RouterLink } from 'vue-router'
</script>

<style scoped>
.home {
  height: 100%;
  display: flex;
  flex-direction: column;
}

.title {
  font-size: 30px;
  font-weight: bold;
  text-align: center;
  margin: 20px 0;
  text-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
}

.cards-1,
.cards-2 {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 12px;
  width: 100%;
}

.cards-1 {
  flex: 1;
}

.cards-2 {
  flex: 1;
}

.card {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border-radius: 16px;
  padding: 12px;
  color: white;
  text-decoration: none;
  transition:
    transform 0.3s ease,
    background 0.3s ease;
  display: flex;
  flex-direction: column;
  height: 100%;
  align-items: center;
  text-align: center;
}

.card:hover {
  transform: scale(1.02);
  background: rgba(255, 255, 255, 0.15);
}

.card-icon {
  width: 60px;
  height: 60px;
  margin-bottom: 8px;
  flex-shrink: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.card-icon img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.card h2 {
  font-size: 16px;
  margin-bottom: 6px;
  font-weight: 600;
  flex-shrink: 0;
}

.card p {
  font-size: 11px;
  line-height: 1.3;
  opacity: 0.8;
  margin: 0;
  overflow: hidden;
  display: -webkit-box;
  -webkit-line-clamp: 4;
  -webkit-box-orient: vertical;
}

@media screen and (min-width: 390px) {
  .card {
    padding: 16px;
  }

  .card-icon {
    width: 80px;
    height: 80px;
    margin-bottom: 12px;
  }

  .card h2 {
    font-size: 18px;
    margin-bottom: 8px;
  }

  .card p {
    font-size: 12px;
    line-height: 1.4;
  }
}
</style>
