<template>
  <section class="bg-white text-gray-900 py-20 px-6">
    <div class="max-w-6xl mx-auto flex flex-col md:flex-row items-center justify-between gap-10">
      <!-- Teks CTA -->
      <div class="md:w-1/2 space-y-6 text-center md:text-left">
        <h2 class="text-4xl md:text-5xl font-bold leading-tight">
          Gadget Bermasalah? Fix Gadget Solusinya!
        </h2>
        <p class="text-lg text-gray-700">
          Kami hadir dengan pelayanan cepat, profesional, dan terpercaya untuk menyelesaikan masalah gadget Anda. Ayo, konsultasikan sekarang!
        </p>
        <NuxtLink
          to="/contact"
          class="inline-block bg-red-600 hover:bg-red-700 text-white font-semibold px-6 py-3 rounded-lg shadow-md transition transform hover:scale-105"
        >
          Hubungi Kami Sekarang
        </NuxtLink>
      </div>

      <!-- Gambar Ilustrasi -->
      <div class="md:w-1/2 flex justify-center">
        <img
          src="/img/logo.png"
          alt="Gadget Support"
          class="w-40 md:w-60 lg:w-72 object-contain"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
// Tidak ada script khusus
</script>
