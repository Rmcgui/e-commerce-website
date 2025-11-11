<template>
  <div>
    <!-- Hero Section -->
    <section class="bg-gradient-to-r from-primary-600 to-primary-800 text-white">
      <div class="container mx-auto px-4 py-20">
        <div class="max-w-3xl">
          <h1 class="text-5xl md:text-6xl font-bold mb-6">
            Welcome to ShopHub
          </h1>
          <p class="text-xl md:text-2xl mb-8 text-primary-100">
            Discover amazing products at unbeatable prices. Your satisfaction is our priority.
          </p>
          <div class="flex flex-col sm:flex-row gap-4">
            <NuxtLink to="/products" class="btn-primary bg-white text-primary-600 hover:bg-gray-100 text-center">
              Shop Now
            </NuxtLink>
            <button class="btn-secondary bg-primary-700 hover:bg-primary-600 text-white border-0">
              Learn More
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Features Section -->
    <section class="py-16 bg-white">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div class="text-center p-6">
            <div class="w-16 h-16 bg-primary-100 rounded-full flex items-center justify-center mx-auto mb-4">
              <svg class="w-8 h-8 text-primary-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
              </svg>
            </div>
            <h3 class="text-xl font-semibold mb-2">Quality Products</h3>
            <p class="text-gray-600">Carefully curated selection of premium items</p>
          </div>

          <div class="text-center p-6">
            <div class="w-16 h-16 bg-primary-100 rounded-full flex items-center justify-center mx-auto mb-4">
              <svg class="w-8 h-8 text-primary-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </div>
            <h3 class="text-xl font-semibold mb-2">Best Prices</h3>
            <p class="text-gray-600">Competitive pricing with regular discounts</p>
          </div>

          <div class="text-center p-6">
            <div class="w-16 h-16 bg-primary-100 rounded-full flex items-center justify-center mx-auto mb-4">
              <svg class="w-8 h-8 text-primary-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 10h18M7 15h1m4 0h1m-7 4h12a3 3 0 003-3V8a3 3 0 00-3-3H6a3 3 0 00-3 3v8a3 3 0 003 3z" />
              </svg>
            </div>
            <h3 class="text-xl font-semibold mb-2">Secure Checkout</h3>
            <p class="text-gray-600">Safe and encrypted payment processing</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Featured Products -->
    <section class="py-16 bg-gray-50">
      <div class="container mx-auto px-4">
        <div class="text-center mb-12">
          <h2 class="text-4xl font-bold mb-4">Featured Products</h2>
          <p class="text-gray-600 text-lg">Check out our special offers and deals</p>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 mb-8">
          <ProductCard
            v-for="product in productsStore.featuredProducts"
            :key="product.id"
            :product="product"
          />
        </div>

        <div class="text-center">
          <NuxtLink to="/products" class="btn-primary">
            View All Products
          </NuxtLink>
        </div>
      </div>
    </section>

    <!-- Categories Section -->
    <section class="py-16 bg-white">
      <div class="container mx-auto px-4">
        <h2 class="text-4xl font-bold text-center mb-12">Shop by Category</h2>
        
        <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
          <div
            v-for="category in categories"
            :key="category.name"
            class="card cursor-pointer hover:shadow-xl transition-shadow duration-300"
            @click="goToCategory(category.name)"
          >
            <div class="aspect-square bg-gradient-to-br from-primary-100 to-primary-200 flex items-center justify-center">
              <span class="text-6xl">{{ category.icon }}</span>
            </div>
            <div class="p-4 text-center">
              <h3 class="font-semibold text-lg">{{ category.name }}</h3>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-16 bg-primary-600 text-white">
      <div class="container mx-auto px-4 text-center">
        <h2 class="text-4xl font-bold mb-4">Ready to Start Shopping?</h2>
        <p class="text-xl mb-8 text-primary-100">
          Join thousands of satisfied customers today
        </p>
        <NuxtLink to="/products" class="btn-primary bg-white text-primary-600 hover:bg-gray-100">
          Browse Products
        </NuxtLink>
      </div>
    </section>
  </div>
</template>

<script setup>
import { useProductsStore } from '~/stores/products'
import { useRouter } from 'vue-router'

const productsStore = useProductsStore()
const router = useRouter()

const categories = [
  { name: 'Electronics', icon: '💻' },
  { name: 'Fashion', icon: '👕' },
  { name: 'Sports', icon: '⚽' },
  { name: 'Lifestyle', icon: '🏠' }
]

const goToCategory = (categoryName) => {
  productsStore.setCategory(categoryName)
  router.push('/products')
}

// Load cart from localStorage on mount
onMounted(() => {
  const cartStore = useCartStore()
  cartStore.loadFromLocalStorage()
})
</script>
