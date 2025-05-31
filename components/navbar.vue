<template>
  <nav class="bg-white shadow-md fixed w-full z-50">
    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
      <!-- Hamburger di kiri untuk mobile -->
      <div class="md:hidden">
        <button @click="toggleMenu" class="text-gray-800 focus:outline-none">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path v-if="!isOpen" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16" />
            <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>

      <!-- MENU TENGAH -->
      <div class="hidden md:flex absolute left-1/2 transform -translate-x-1/2 space-x-8">
        <a href="#" class="text-gray-800 hover:text-blue-600 font-medium transition duration-200">
          Home
        </a>
        <a href="#about" class="text-gray-800 hover:text-blue-600 font-medium transition duration-200">
          About
        </a>
        <a href="#product" class="text-gray-800 hover:text-blue-600 font-medium transition duration-200">
          Product
        </a>
        <a href="#contact" class="text-gray-800 hover:text-blue-600 font-medium transition duration-200">
          Contact
        </a>
      </div>
    </div>

    <!-- MOBILE MENU -->
    <div v-if="isOpen" class="md:hidden px-4 pt-2 pb-3 space-y-1 bg-white shadow-md text-center">
      <a href="#home" class="block text-gray-800 hover:text-blue-600 font-medium transition duration-200" @click="closeMenu">
        Home
      </a>
      <a href="#about" class="block text-gray-800 hover:text-blue-600 font-medium transition duration-200" @click="closeMenu">
        About
      </a>
      <a href="#produk" class="block text-gray-800 hover:text-blue-600 font-medium transition duration-200" @click="closeMenu">
        Product
      </a>
      <a href="#contact" class="block text-gray-800 hover:text-blue-600 font-medium transition duration-200" @click="closeMenu">
        Contact
      </a>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const isOpen = ref(false)
const toggleMenu = () => {
  isOpen.value = !isOpen.value
}
const closeMenu = () => {
  isOpen.value = false
}
</script>
