<script setup>
import { ref } from 'vue'
import AppHeader from './components/AppHeader.vue'
import AppErrors from './components/AppErrors.vue'

// Состояние для управления видимостью попапа
const isPopupVisible = ref(false)

// Функция для переключения видимости попапа
const togglePopup = () => {
  isPopupVisible.value = !isPopupVisible.value
}
</script>

<template>
  <!-- Подключаем AppHeader и слушаем событие openPopup -->
  <AppHeader @openPopup="togglePopup" />

  <!-- Попап -->
  <div v-if="isPopupVisible">
    <!-- Затемнение фона -->
    <div
      class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-70"
      @click="togglePopup"
    ></div>

    <!-- Контейнер с формой -->
    <div class="flex justify-center items-center fixed top-0 left-0 h-full w-full z-20">
      <div class="bg-[#2D3035] w-3/5 h-3/5 p-8 rounded-3xl">
        <h1 class="text-3xl font-bold flex justify-center mt-16 text-white">Форма авторизации</h1>
        <form class="flex flex-col mt-16" name="auth">
          <input
            type="text"
            placeholder="Введите логин"
            class="px-4 border h-28 rounded-xl text-3xl"
          />
          <input
            type="password"
            placeholder="Введите пароль"
            class="px-4 border h-28 mt-14 rounded-xl text-3xl"
          />
        </form>
        <button
          @click="togglePopup"
          class="text-4xl text-white mt-12 bg-[#EA0022] justify-center rounded-md h-20 w-52 hover:opacity-80"
        >
          Отправить
        </button>
      </div>
    </div>
  </div>

  <!-- Дополнительные компоненты -->
  <AppErrors />
</template>
