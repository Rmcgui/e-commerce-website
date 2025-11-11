<template>
  <footer class="bg-gray-900 text-gray-300 mt-16">
    <div class="container mx-auto px-4 py-12">
      <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
        <!-- Company Info -->
        <div>
          <div class="flex items-center space-x-2 mb-4">
            <div class="w-8 h-8 bg-primary-600 rounded-lg flex items-center justify-center">
              <span class="text-white font-bold">E</span>
            </div>
            <span class="text-xl font-bold text-white">ShopHub</span>
          </div>
          <p class="text-sm">
            Your trusted online marketplace for quality products at great prices.
          </p>
        </div>

        <!-- Quick Links -->
        <div>
          <h3 class="text-white font-semibold mb-4">Quick Links</h3>
          <ul class="space-y-2">
            <li>
              <NuxtLink to="/" class="hover:text-white transition-colors">
                Home
              </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/products" class="hover:text-white transition-colors">
                Products
              </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/checkout" class="hover:text-white transition-colors">
                Checkout
              </NuxtLink>
            </li>
          </ul>
        </div>

        <!-- Categories -->
        <div>
          <h3 class="text-white font-semibold mb-4">Categories</h3>
          <ul class="space-y-2">
            <li><a href="#" class="hover:text-white transition-colors">Electronics</a></li>
            <li><a href="#" class="hover:text-white transition-colors">Fashion</a></li>
            <li><a href="#" class="hover:text-white transition-colors">Sports</a></li>
            <li><a href="#" class="hover:text-white transition-colors">Lifestyle</a></li>
          </ul>
        </div>

        <!-- Contact -->
        <div>
          <h3 class="text-white font-semibold mb-4">Contact Us</h3>
          <ul class="space-y-2 text-sm">
            <li>Email: support@shophub.com</li>
            <li>Phone: +1 (555) 123-4567</li>
            <li>Address: 123 Commerce St, City, Country</li>
          </ul>
        </div>
      </div>

      <div class="border-t border-gray-800 mt-8 pt-8 text-center text-sm">
        <p>&copy; {{ new Date().getFullYear() }} ShopHub. All rights reserved.</p>
      </div>
    </div>
  </footer>
</template>

<script setup>
// Footer component
</script>
