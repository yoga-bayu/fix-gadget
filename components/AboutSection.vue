<template>
  <section id="about" class="py-12 px-4 text-center bg-white">
    <!-- Judul -->
    <h1 class="text-3xl md:text-4xl font-bold mb-8 text-gray-800">About</h1>

    <!-- Grid Gambar -->
    <div class="flex flex-wrap justify-center gap-4 mb-8">
      <img
        v-for="(image, index) in images"
        :key="index"
        :src="image"
        :alt="`Gallery image ${index + 1}`"
        class="w-24 h-24 md:w-32 md:h-32 object-cover cursor-pointer rounded shadow hover:scale-105 transition-transform duration-300"
        @click="openImage(image)"
      />
    </div>

    <!-- Overlay Gambar Fullscreen -->
    <div
      v-if="selectedImage"
      class="fixed inset-0 bg-black/60 backdrop-blur-sm flex items-center justify-center z-50"
      @click="closeImage"
    >
      <img
        :src="selectedImage"
        class="max-w-[90%] max-h-[80%] rounded-lg shadow-lg transition-transform duration-300 scale-100 hover:scale-105"
      />
    </div>

    <!-- Teks Penjelasan -->
    <div class="max-w-3xl mx-auto text-gray-700 space-y-6 text-sm md:text-base mt-8 px-4 text-justify">
      <p>
        <strong>Fix Gadget</strong> adalah penyedia layanan servis gadget terpercaya yang hadir dengan komitmen untuk memberikan solusi terbaik bagi permasalahan perangkat elektronik Anda. Kami memahami betapa pentingnya peran gadget dalam aktivitas sehari-hari, mulai dari komunikasi, pekerjaan, hingga hiburan. Oleh karena itu, kami bertekad untuk memberikan layanan cepat, akurat, dan transparan.
      </p>

      <p>
        Sejak didirikan pada tahun 2020, Fix Gadget telah melayani ribuan pelanggan dengan berbagai kebutuhan perbaikan gadget, mulai dari smartphone, tablet, hingga laptop. Dengan tim teknisi profesional yang berpengalaman, kami senantiasa mengikuti perkembangan teknologi agar dapat memberikan hasil servis yang memuaskan dan sesuai standar pabrik.
      </p>

      <p>
        <strong>Visi kami</strong> adalah menjadi pusat layanan servis gadget terpercaya dan terdepan di Indonesia, yang tidak hanya mengutamakan kualitas, tetapi juga kenyamanan dan kepercayaan pelanggan. Kami ingin menjadi solusi utama bagi masyarakat ketika perangkat mereka mengalami masalah, tanpa harus merasa khawatir atau bingung.
      </p>

      <p>
        <strong>Misi kami</strong> adalah menyediakan layanan servis gadget yang cepat, akurat, dan transparan dengan harga yang kompetitif. Kami berkomitmen untuk selalu meningkatkan kualitas pelayanan, memperluas jaringan layanan ke berbagai wilayah, dan memberikan edukasi kepada masyarakat mengenai perawatan gadget yang baik dan benar.
      </p>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const images = [
  '/img/sm.png',
  '/img/lp.png',
  '/img/tv.png',
  '/img/tab.png'
]

const selectedImage = ref(null)

const openImage = (img) => {
  selectedImage.value = img
}

const closeImage = () => {
  selectedImage.value = null
}
</script>
