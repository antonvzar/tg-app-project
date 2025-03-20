<script setup>
import { ref } from 'vue'

const isLogin = ref(true)
const email = ref('')
const password = ref('')
const name = ref('')

const toggleForm = () => {
  isLogin.value = !isLogin.value
}

const handleSubmit = () => {
  // Implement authentication logic here
  console.log('Form submitted')
}
</script>

<template>
  <div class="auth">
    <h1>{{ isLogin ? 'Вход' : 'Регистрация' }}</h1>

    <form @submit.prevent="handleSubmit" class="auth-form">
      <template v-if="!isLogin">
        <div class="form-group">
          <label for="name">Имя</label>
          <input type="text" id="name" v-model="name" required />
        </div>
      </template>

      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" id="email" v-model="email" required />
      </div>

      <div class="form-group">
        <label for="password">Пароль</label>
        <input type="password" id="password" v-model="password" required />
      </div>

      <button type="submit" class="submit-btn">
        {{ isLogin ? 'Войти' : 'Зарегистрироваться' }}
      </button>

      <button type="button" class="toggle-btn" @click="toggleForm">
        {{ isLogin ? 'Создать аккаунт' : 'Уже есть аккаунт?' }}
      </button>
    </form>
  </div>
</template>

<style scoped>
.auth {
  padding: 20px 0;
  max-width: 400px;
  margin: 0 auto;
}

h1 {
  font-size: 32px;
  margin-bottom: 30px;
  text-align: center;
}

.auth-form {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  padding: 20px;
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 5px;
  font-size: 14px;
}

input {
  width: 100%;
  padding: 10px;
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 10px;
  background: rgba(255, 255, 255, 0.1);
  color: white;
  font-size: 16px;
}

input:focus {
  outline: none;
  border-color: rgba(255, 255, 255, 0.5);
}

.submit-btn {
  width: 100%;
  padding: 12px;
  background: rgba(255, 255, 255, 0.2);
  border: none;
  border-radius: 10px;
  color: white;
  font-size: 16px;
  cursor: pointer;
  transition: background 0.3s ease;
  margin-bottom: 10px;
}

.submit-btn:hover {
  background: rgba(255, 255, 255, 0.3);
}

.toggle-btn {
  width: 100%;
  padding: 12px;
  background: transparent;
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 10px;
  color: white;
  font-size: 14px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.toggle-btn:hover {
  background: rgba(255, 255, 255, 0.1);
}
</style>
