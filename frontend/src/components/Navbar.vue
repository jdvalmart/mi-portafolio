<template>
  <header class="bg-gray-900 shadow-md sticky top-0 z-50">
    <div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">
      <router-link to="/" class="text-2xl font-bold text-white">
        Portafolio Jdvalmart
      </router-link>

      <!-- Desktop nav -->
      <nav class="space-x-6 hidden md:block">
        <router-link
          v-for="link in links"
          :key="link.to"
          :to="link.to"
          class="text-white hover:text-blue-600 font-medium transition"
          :class="{ 'text-blue-700 font-semibold': $route.path === link.to }"
        >
          {{ link.label }}
        </router-link>
      </nav>

      <!-- Mobile button -->
      <div class="md:hidden">
        <button @click="isOpen = !isOpen" aria-label="Menú móvil">
          <svg
            class="w-6 h-6 text-gray-700"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile menu -->
    <div v-if="isOpen" class="md:hidden bg-white border-t px-6 pb-4">
      <router-link
        v-for="link in links"
        :key="link.to"
        :to="link.to"
        class="block py-2 text-gray-700 hover:text-blue-600 transition"
        :class="{ 'text-blue-700 font-semibold': $route.path === link.to }"
        @click="isOpen = false"
      >
        {{ link.label }}
      </router-link>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const isOpen = ref(false)

const links = [
  { to: '/', label: 'Inicio' },
  { to: '/about', label: 'Sobre mí' },
  { to: '/projects', label: 'Proyectos' },
  { to: '/blog', label: 'Blog' },
  { to: '/contact', label: 'Contacto' },
]
</script>
