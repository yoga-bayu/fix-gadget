<template>
  <section id="contact" class="min-h-screen flex items-center justify-center bg-gray-50 px-4 py-12">
    <div class="max-w-xl w-full bg-white p-8 rounded-lg shadow-lg">
      <h2 class="text-3xl font-bold text-gray-800 mb-6 text-center">Hubungi Kami</h2>
      <form @submit.prevent="handleSubmit" class="space-y-6">
        <div>
          <label for="name" class="block text-gray-700 font-semibold mb-1">Nama Lengkap</label>
          <input
            type="text"
            id="name"
            v-model="form.name"
            required
            placeholder="Masukkan nama Anda"
            class="w-full px-4 py-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-red-600 transition"
          />
        </div>

        <div>
          <label for="email" class="block text-gray-700 font-semibold mb-1">Email</label>
          <input
            type="email"
            id="email"
            v-model="form.email"
            required
            placeholder="contoh@mail.com"
            class="w-full px-4 py-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-red-600 transition"
          />
        </div>

        <div>
          <label for="subject" class="block text-gray-700 font-semibold mb-1">Subjek</label>
          <input
            type="text"
            id="subject"
            v-model="form.subject"
            placeholder="Judul pesan"
            class="w-full px-4 py-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-red-600 transition"
          />
        </div>

        <div>
          <label for="message" class="block text-gray-700 font-semibold mb-1">Pesan</label>
          <textarea
            id="message"
            v-model="form.message"
            required
            rows="5"
            placeholder="Tulis pesan Anda di sini..."
            class="w-full px-4 py-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-red-600 transition resize-none"
          ></textarea>
        </div>

        <button
          type="submit"
          :disabled="loading"
          class="w-full bg-red-600 hover:bg-red-700 text-white font-bold py-3 rounded-md transition disabled:opacity-50"
        >
          {{ loading ? 'Mengirim...' : 'Kirim Pesan' }}
        </button>
      </form>

      <p v-if="successMessage" class="mt-4 text-green-600 font-semibold text-center">
        {{ successMessage }}
      </p>
    </div>
  </section>
</template>

<script setup>
import { reactive, ref } from 'vue'

const form = reactive({
  name: '',
  email: '',
  subject: '',
  message: ''
})

const loading = ref(false)
const successMessage = ref('')

const handleSubmit = () => {
  loading.value = true
  successMessage.value = ''

  // Simulasi request API / pengiriman pesan
  setTimeout(() => {
    loading.value = false
    successMessage.value = 'Terima kasih! Pesan Anda telah terkirim.'
    // Reset form
    form.name = ''
    form.email = ''
    form.subject = ''
    form.message = ''
  }, 2000)
}
</script>
