<script setup>
import AboutSection from '@/components/AboutSection.vue'
import ProductSection from '@/components/ProductSection.vue'
import ContactSection from '@/components/ContactSection.vue'
import CallToAction from '@/components/CallToAction.vue'
import Footer from '@/components/Footer.vue'
import Navbar from '@/components/Navbar.vue'
</script>

<template>
  <div>
    <Navbar />>
    <!-- Section: Home -->
    <section
      id="home"
      class="min-h-screen bg-cover bg-center flex items-center"
      :style="`background-image: url('/img/bg1.png')`"
    >
      <div class="text-white p-6 md:p-12 lg:p-20 max-w-3xl animate-fade-in">
        <h1 class= "text-4xl md:text-5xl lg:text-6xl font-bold mb-4">
          Fix Gadget
        </h1>
        <p class="birthstone-regular text-base md:text-lg lg:text-4xl mb-6">
          Solusi Cepat dan Tepat untuk Gadget Anda
        </p>
        <a
          href="#product"
          class="inline-block px-6 py-3 bg-red-600 hover:bg-red-700 text-white rounded-lg text-sm md:text-base transition-all duration-300"
        >
          Lihat Produk
        </a>
      </div>
    </section>

    <!-- Section: About -->
    <AboutSection />

    <!-- Section: Product -->
    <ProductSection />

    <!-- Section: Contact -->
    <ContactSection />

    <!-- Call to Action -->
    <CallToAction />

    <!-- Footer -->
    <Footer />
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Birthstone&display=swap');

@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fade-in 1s ease-out;
}

.birthstone-regular {
  font-family: "Birthstone", cursive;
  font-weight: 400;
  font-style: normal;
}
</style>

<style>
html {
  scroll-behavior: smooth;
}
</style>
