<script setup>
import { onMounted, ref } from "vue";

const isOpen = ref(false);
</script>

<template>
  <nav
    class="fixed top-6 left-1/2 transform -translate-x-1/2
           bg-white/50 backdrop-blur-lg rounded-full shadow-lg px-10 py-5
           flex justify-between items-center max-w-7xl w-[92%] z-50 dark">

    <!-- Logo -->
    <h1 class="font-bold text-xl sm:text-2xl text-green-600 tracking-wide dark:text-white">MyPortfolio</h1>

    <!-- Desktop Navigation -->
    <ul class="hidden lg:flex items-center space-x-8">
      <li><a href="#hero" class="text-gray-700 hover:text-green-600 hover:font-semibold transition-all duration-500 dark:text-white dark:hover:text-green-300">Home</a></li>
      <li><a href="#about" class="text-gray-700 hover:text-green-600 hover:font-semibold transition-all duration-500 dark:text-white dark:hover:text-green-300">About</a></li>
      <li><a href="#tech" class="text-gray-700 hover:text-green-600 hover:font-semibold transition-all duration-500 dark:text-white dark:hover:text-green-300">Tech Stack</a></li>
      <li><a href="#projects" class="text-gray-700 hover:text-green-600 hover:font-semibold transition-all duration-500 dark:text-white dark:hover:text-green-300">Projects</a></li>
    </ul>

    <!-- Mobile Hamburger -->
    <button @click="isOpen = !isOpen" class="lg:hidden focus:outline-none">
      <svg v-if="!isOpen" xmlns="http://www.w3.org/2000/svg" class="w-7 h-7 text-gray-700" fill="none" viewBox="0 0 24 24"
        stroke="currentColor" stroke-width="2">
        <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
      </svg>
      <svg v-else xmlns="http://www.w3.org/2000/svg" class="w-7 h-7 text-gray-700" fill="none" viewBox="0 0 24 24"
        stroke="currentColor" stroke-width="2">
        <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
      </svg>
    </button>

    <!-- Mobile Menu -->
    <transition name="fade">
      <ul v-if="isOpen"
        class="absolute top-20 left-1/2 transform -translate-x-1/2
               bg-white/90 backdrop-blur-lg shadow-lg rounded-2xl flex flex-col items-center justify-end
               space-y-6 py-6 px-10 w-[85%] max-w-sm lg:hidden">
        <li><a @click="isOpen = false" href="#hero" class="text-gray-700 hover:text-green-600 transition">Home</a></li>
        <li><a @click="isOpen = false" href="#about" class="text-gray-700 hover:text-green-600 transition">About</a></li>
        <li><a @click="isOpen = false" href="#tech" class="text-gray-700 hover:text-green-600 transition">Tech Stack</a></li>
        <li><a @click="isOpen = false" href="#projects" class="text-gray-700 hover:text-green-600 transition">Projects</a></li>
      </ul>
    </transition>
  </nav>
</template>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>
