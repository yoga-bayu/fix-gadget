<template>
  <div id="product" class="py-12 px-4 bg-gray-50 min-h-screen">
    <h1 class="text-3xl md:text-4xl font-bold mb-8 text-gray-800 text-center">Produk Kami</h1>

    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-6 max-w-7xl mx-auto">
      <div
        v-for="(product, index) in products"
        :key="index"
        class="cursor-pointer rounded-lg overflow-hidden shadow-md hover:shadow-xl transition-shadow"
        @click="openProduct(product)"
      >
        <img
          :src="product.image"
          :alt="product.name"
          class="w-full h-48 object-cover"
        />
        <div class="p-4 bg-gray-50 text-center font-semibold text-gray-800">
          {{ product.name }}
        </div>
      </div>
    </div>

    <!-- Popup Produk -->
    <div
      v-if="selectedProduct"
      class="fixed inset-0 backdrop-blur-sm flex items-center justify-center z-50 p-4"
      @click.self="closeProduct"
    >
      <div
        class="bg-white bg-opacity-90 rounded-lg shadow-lg max-w-3xl w-full overflow-hidden"
      >
        <img
          :src="selectedProduct.image"
          :alt="selectedProduct.name"
          class="w-full max-h-[60vh] object-contain"
        />
        <div class="p-6 text-center">
          <h3 class="text-2xl font-bold mb-4 text-gray-900">
            {{ selectedProduct.name }}
          </h3>
          <p class="mb-6 text-gray-700 whitespace-pre-line">
            {{ selectedProduct.description }}
          </p>
          <a
            :href="selectedProduct.link"
            target="_blank"
            class="inline-block px-6 py-3 bg-red-600 hover:bg-red-700 text-white rounded-lg font-semibold transition"
          >
            Lihat Detail
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const products = [
  {
    name: 'Motorola',
    image: '/img/motorola.png',
    description: 'Motorola G45 5G 8/256GB - Up to 16GB Extended RAM - Snapdragon 6s Gen 3 - 6.5 inch Screen Size ',
    link: 'https://shopee.co.id/Motorola-G45-5G-8-256GB-Up-to-16GB-Extended-RAM-Snapdragon-6s-Gen-3-6.5-inch-Screen-Size-Gorilla-Glass-3-120Hz-50MP-Main-Camera-16MP-Selfie-Camera-5000mAh-NFC-Dolby-Atmos-Stereo-Speaker-Bonus-Charger-20W-Clear-Case-i.1456663090.25140996101?sp_atk=464356fc-0b22-4b25-86fe-6abb268182e3&xptdk=464356fc-0b22-4b25-86fe-6abb268182e3'
  },
  {
    name: 'Oppo A3s',
    image: '/img/oppoa3s.png',
    description: 'HP OPPO A3S 6/128GB 4G LTE Smartphone Garansi 12 bulan Promosi',
    link: 'https://shopee.co.id/HP-OPPO-A3S-6-128GB-4G-LTE-Smartphone-Garansi-12-bulan-Promosi-i.1248781014.26685422004?sp_atk=cb98102c-64b5-4af7-9389-ab81128b8766&xptdk=cb98102c-64b5-4af7-9389-ab81128b8766'
  },
  {
    name: 'Iphone 14 Plus',
    image: '/img/iphone14plus.png',
    description: 'lphone 14 / 14 plus second inter like new original',
    link: 'https://shopee.co.id/lphone-14-14-plus-second-inter-like-new-original-i.295818274.26979757664?sp_atk=5c7b9f0c-2e94-4144-b4b4-d597c3078318&xptdk=5c7b9f0c-2e94-4144-b4b4-d597c3078318'
  },
  {
    name: 'Xiaomi Redmi 12',
    image: '/img/redmi12.png',
    description: 'XIAOMI REDMI 12 RAM 8 / 256 GB FULLSET - GARANSI 1 TAHUN',
    link: 'https://shopee.co.id/XIAOMI-REDMI-12-RAM-8-256-GB-FULLSET-GARANSI-1-TAHUN-i.482414408.27264458163?sp_atk=25cc85eb-9208-41d2-962a-42f1d88921df&xptdk=25cc85eb-9208-41d2-962a-42f1d88921df'
  },
  {
    name: 'Laptop Slims Toshiba G83',
    image: '/img/slims.png',
    description: 'LAPTOP SLIMS DAN RINGAN TOSHIBA G83 i7 GEN 12th IRIS XE RAM 16GB SSD BERGARANSI',
    link: 'https://shopee.co.id/LAPTOP-SLIMS-DAN-RINGAN-TOSHIBA-G83-i7-GEN-12th-IRIS-XE-RAM-16GB-SSD-BERGARANSI-i.20247673.25794903073?sp_atk=fd047622-dfa5-41be-8cf0-3d247a349244&xptdk=fd047622-dfa5-41be-8cf0-3d247a349244'
  },
  {
    name: 'Tablet Z',
    image: '/img/thinkpadt470s.png',
    description: 'Laptop Lenovo Thinkpad T470s T470 Core i7/ i5 Gen 7 Ram 32GB SSD 1TB - Second Murah Bergaransi |SLIM',
    link: 'https://shopee.co.id/Laptop-Lenovo-Thinkpad-T470s-T470-Core-i7-i5-Gen-7-Ram-32GB-SSD-1TB-Second-Murah-Bergaransi-SLIM-i.20347114.21782365148?sp_atk=fc5f4d19-76bf-4909-a448-ed4d51d9b668&xptdk=fc5f4d19-76bf-4909-a448-ed4d51d9b668'
  },
  {
    name: 'Ipad Pro 9.7',
    image: '/img/ipadpro.png',
    description: 'IPAD PRO 9.7 9,7INCH 128 128GB WIFI SECOND SEKEN WIFI ONLY',
    link: 'https://shopee.co.id/IPAD-PRO-9.7-9-7INCH-128-128GB-WIFI-SECOND-SEKEN-WIFI-ONLY-i.194040484.29481827332?sp_atk=0afe24b3-ba6f-4b88-9f02-9fce2d864297&xptdk=0afe24b3-ba6f-4b88-9f02-9fce2d864297'
  },
  {
    name: 'TV Digital',
    image: '/img/tvdigital.png',
    description: 'Changhong 40 Inch Newest Android 11 Frameless Smart TV Digital LED TV FHD -Netflix-Youtube-Google Playstore (L40G7N)',
    link: 'https://shopee.co.id/Changhong-40-Inch-Newest-Android-11-Frameless-Smart-TV-Digital-LED-TV-FHD-Netflix-Youtube-Google-Playstore-(L40G7N)-i.202812301.44001650707?sp_atk=3e5b1a7d-12c6-4677-a4d1-0d72de7586b2&xptdk=3e5b1a7d-12c6-4677-a4d1-0d72de7586b2'
  }
]

const selectedProduct = ref(null)

function openProduct(product) {
  selectedProduct.value = product
}

function closeProduct() {
  selectedProduct.value = null
}
</script>
