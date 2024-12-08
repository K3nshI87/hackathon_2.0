<script setup>
import { defineEmits } from 'vue'

// Определяем событие, которое будет эмитироваться в родительский компонент
const emit = defineEmits(['openPopup'])

// Создаём функцию-обработчик клика, которая вызывает emit
const handleOpenPopup = () => {
  emit('openPopup')
}
</script>

<template>
  <header class="bg-[#2D3035] w-screen h-28 shadow-lg flex items-center justify-between rounded-md">
    <div class="flex items-center h-28 w-1/6 justify-between">
      <img class="ml-5 h-16 w-16" src="/Logo_RGB.svg" alt="Logo" />
      <h1 class="text-3xl ml-4 text-white">X</h1>
      <h1 class="text-3xl ml-5 font-bold text-white">МТС ЭГСПЕРТЫ</h1>
    </div>
    <Button
      @click="handleOpenPopup"
      class="text-3xl bg-[#EA0022] mr-5 rounded-md h-16 w-56 cursor-pointer hover:opacity-80 text-white transition mt-15"
    >
      Авторизация
    </Button>
  </header>
</template>
