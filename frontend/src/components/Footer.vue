<template>
  <footer class="bg-gray-900 text-white py-6 mt-2">
    <div class="max-w-6xl mx-auto px-6 text-center text-sm">
      <p>© {{ year }} Jdvalmart. Todos los derechos reservados.</p>
      <div class="flex justify-center gap-4 mt-2 text-blue-400">
        <a href="https://github.com/jdvalmart" target="_blank" class="hover:underline">GitHub</a>
        <a href="https://www.linkedin.com/in/jdvalmart/" target="_blank" class="hover:underline">LinkedIn</a>
        <a href="mailto:tucorreo@email.com" class="hover:underline">Email</a>
      </div>
    </div>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear()
</script>
