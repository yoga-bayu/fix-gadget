<template>
  <div class="py-12 px-4 text-center bg-white">
    <!-- Judul -->
    <h1 class="text-3xl md:text-4xl font-bold mb-8 text-gray-800">About</h1>

    <!-- Grid Gambar -->
    <div class="flex flex-wrap justify-center gap-4 mb-8">
      <img
        v-for="(image, index) in images"
        :key="index"
        :src="image"
        alt="Gallery"
        class="w-24 h-24 md:w-32 md:h-32 object-cover cursor-pointer rounded shadow hover:scale-105 transition-transform"
        @click="openImage(image)"
      />
    </div>

    <!-- Popup Gambar -->
    <div
      v-if="selectedImage"
      class="fixed inset-0 bg-black bg-opacity-70 backdrop-blur-sm flex items-center justify-center z-50"
      @click="closeImage"
    >
      <img :src="selectedImage" class="max-w-[90%] max-h-[80%] rounded-lg shadow-lg" />
    </div>

    <!-- Teks Penjelasan -->
    <div class="max-w-3xl mx-auto text-gray-700 space-y-6 text-sm md:text-base">
      <p><strong>Fix Gadget</strong> adalah penyedia layanan servis gadget terpercaya dan profesional.</p>
      <p><strong>Sejarah:</strong> Didirikan pada tahun 2020, Fix Gadget hadir untuk menjawab kebutuhan masyarakat akan layanan cepat dan tepat dalam menangani kerusakan gadget.</p>
      <p><strong>Visi:</strong> Menjadi pusat layanan gadget terdepan dengan pelayanan terbaik di seluruh Indonesia.</p>
      <p><strong>Misi:</strong> Memberikan solusi servis yang cepat, transparan, dan berkualitas tinggi kepada setiap pelanggan.</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const images = [
  '/img/gallery1.jpg',
  '/img/gallery2.jpg',
  '/img/gallery3.jpg',
  '/img/gallery4.jpg'
]

const selectedImage = ref(null)

const openImage = (img) => {
  selectedImage.value = img
}

const closeImage = () => {
  selectedImage.value = null
}
</script>

<style scoped>
/* Optional animation */
img {
  transition: transform 0.3s ease;
}
</style>
