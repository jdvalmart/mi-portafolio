<template>
  <div
    class="bg-white rounded-xl shadow-md p-5 hover:shadow-xl transition duration-300 ease-in-out"
  >
    <h3 class="text-gray-600 mb-4">{{ title }}</h3>
    <p class="text-gray-600 mb-4">{{ description }}</p>

    <div class="flex flex-wrap gap-2 mb-4">
      <span
        v-for="(tech, i) in technologies"
        :key="i"
        class="bg-blue-100 text-blue-800 px-2 py-1 rounded text-sm"
      >
        {{ tech }}
      </span>
    </div>

    <a
      :href="link"
      target="_blank"
      rel="noopener noreferrer"
      class="text-blue-600 hover:underline font-medium"
    >
      Ver repositorio
    </a>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  description: String,
  technologies: Array,
  link: String,
})
</script>
