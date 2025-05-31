<template>
  <footer class="bg-gray-900 text-white py-10 px-6">
    <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-4 gap-10">
      <!-- Kolom 1: Logo dan Sosial Media -->
      <div>
        <img src="/img/logopth.png" alt="Fix Gadget Logo" class="w-32 mb-4" />
        <div class="flex space-x-4">
          <a href="https://instagram.com" target="_blank" aria-label="Instagram">
            <svg class="w-6 h-6 hover:text-red-500" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M7.75 2h8.5A5.75 5.75 0 0122 7.75v8.5A5.75 5.75 0 0116.25 22h-8.5A5.75 5.75 0 012 16.25v-8.5A5.75 5.75 0 017.75 2zm0 1.5A4.25 4.25 0 003.5 7.75v8.5A4.25 4.25 0 007.75 20.5h8.5a4.25 4.25 0 004.25-4.25v-8.5A4.25 4.25 0 0016.25 3.5h-8.5zM12 7a5 5 0 110 10 5 5 0 010-10zm0 1.5a3.5 3.5 0 100 7 3.5 3.5 0 000-7zm5.25-.75a.75.75 0 110 1.5.75.75 0 010-1.5z"
              />
            </svg>
          </a>
          <a href="https://facebook.com" target="_blank" aria-label="Facebook">
            <svg class="w-6 h-6 hover:text-blue-500" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M22 12a10 10 0 10-11.5 9.95v-7.05h-2.1v-2.9h2.1v-2.2c0-2.1 1.26-3.25 3.18-3.25.92 0 1.87.16 1.87.16v2.05h-1.05c-1.04 0-1.36.64-1.36 1.3v1.94h2.32l-.37 2.9h-1.95v7.05A10 10 0 0022 12z"
              />
            </svg>
          </a>
        </div>
      </div>

      <!-- Kolom 2: Menu -->
      <div>
        <h3 class="font-semibold text-lg mb-4">Menu</h3>
        <ul class="space-y-2">
          <li><NuxtLink to="/" class="hover:text-gray-300">Home</NuxtLink></li>
          <li><NuxtLink to="#about" class="hover:text-gray-300">About</NuxtLink></li>
          <li><NuxtLink to="#product" class="hover:text-gray-300">Product</NuxtLink></li>
          <li><NuxtLink to="#contact" class="hover:text-gray-300">Contact</NuxtLink></li>
        </ul>
      </div>

      <!-- Kolom 3: Visi Misi -->
      <div>
        <h3 class="font-semibold text-lg mb-4">Visi & Misi</h3>
        <p class="text-sm text-gray-300">
          <strong>Visi:</strong> Menjadi pusat layanan gadget terdepan dengan pelayanan terbaik di seluruh Indonesia.
        </p>
        <p class="mt-2 text-sm text-gray-300">
          <strong>Misi:</strong> Memberikan solusi servis yang cepat, transparan, dan berkualitas tinggi kepada setiap pelanggan.
        </p>
      </div>

      <!-- Kolom 4: Alamat -->
      <div>
        <h3 class="font-semibold text-lg mb-4">Alamat</h3>
        <p class="text-sm text-gray-300">
          Jl. Cendrawasih<br />
          Jakarta Timur<br />
          Email: fixgadget@gmail.com
        </p>
      </div>
    </div>

    <!-- Copyright -->
    <div class="mt-10 text-center text-sm text-gray-400">
      © 2025 Fix Gadget. All rights reserved.
    </div>
  </footer>
</template>

<script setup>
// Tidak ada script khusus
</script>
