<template>
  <div class="min-h-screen bg-black text-white">
    <nav class="fixed top-0 left-0 right-0 z-50 bg/black/80 backdrop-blur-sm border-b border-gray-800">
      <div class="container mx-auto px-6 py-4">
        <div class="flex items-center justify-between">
          <NuxtLink to="/" class="text-xl font-bold hover_text-green-500 transition-colors">
            Dylan Thomas
          </NuxtLink>

          <div class="hidden md:flex items-center gap-8">
            <NuxtLink
                v-for="link in navLinks"
                :key="link.to"
                :to="link.to"
                class="text-gray-400 hover:text-white transition-colors">
              {{ link.label }}
            </NuxtLink>
          </div>

          <button @click="mobileMenuOpen = !mobileMenuOpen" class="md:hidden text-gray-400 hover:text-white">
            <span class="sr-only">Menu</span>
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path
                  v-if="!mobileMenuOpen"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 6h16M4 12h16M4 18h16"
              />
              <path
                  v-else
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>

        <div v-if="mobileMenuOpen" class="md:hidden mt-4 pb-4 flex flex-col gap-4">
          <NuxtLink
              v-for="link in navLinks"
              :key="link.to"
              :to="link.to"
              @click="mobileMenuOpen = false"
              class="text-gray-400 hover:text-white transition-colors"
          >
            {{ link.label }}
          </NuxtLink>
        </div>
      </div>
    </nav>

    <main class="pt-20">
      <slot />
    </main>

    <footer class="border-t border-gray-800 mt-20">
      <div class="container mx-auto px-6 py-8">
        <div class="flex flex-col md:flex-row justify-between items-center gap-4">
          <p class="text-gray-400 text-sm">
            &copy; {{ new Date().getFullYear() }} Dylan Thomas
          </p>

          <div class="flex gap-6">
            <a href="https://www.linkedin.com/in/dylan-thomas-5b80b1238/" target="_blank" class="text-gray-400 hover:text-white transition-colors">LinkedIn</a>
            <a href="https://github.com/dthomas1108" target="_blank" class="text-gray-400 hover:text-white transition-colors">Github</a>
          </div>

        </div>
      </div>
    </footer>

  </div>
</template>

<script setup>
import { ref } from 'vue';

const mobileMenuOpen = ref(false);

const navLinks = [
  { to: '/', label: 'Home' },
  { to: '/about', label: 'About' },
  { to: '/experience', label: 'Experience' },
  { to: '/contact', label: 'Contact' },
];
</script>