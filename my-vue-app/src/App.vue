<template>
  <div>
    <h1>Форма регистрации</h1>
    
    <input v-model="name" placeholder="Ваше имя" />
    <input v-model="email" placeholder="Email" />
    
    <button @click="showData">Показать данные</button>
    
    <label>
      <input type="checkbox" v-model="showMessage" />
      Показать сообщение
    </label>
    <p v-if="showMessage">Добро пожаловать, {{ name }}!</p>
    
    <h3>Любимый язык программирования:</h3>
    <label>
      <input type="radio" value="JavaScript" v-model="favoriteLang" />
      JavaScript
    </label>
    <label>
      <input type="radio" value="Python" v-model="favoriteLang" />
      Python
    </label>
    <label>
      <input type="radio" value="Java" v-model="favoriteLang" />
      Java
    </label>
    <p>Вы выбрали: {{ favoriteLang }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const showMessage = ref(false)
const favoriteLang = ref('JavaScript')

const showData = () => {
  console.log('Имя:', name.value)
  console.log('Email:', email.value)
}
</script>
