<template>
  <section class="min-h-screen bg-white text-gray-800 px-6 py-12">
    <div class="max-w-4xl mx-auto">
      <h2 class="text-3xl md:text-4xl font-bold mb-6">Sobre mí</h2>
      <p class="text-lg mb-4">
        Soy un ingeniero de software en formación con experiencia en desarrollo frontend con tecnologías como Vue, React y Tailwind.
      </p>
       <div>
    <h2>Lista de usuarios</h2>
    <ul>
      <li v-for="usuario in usuarios" :key="usuario.id">
        {{ usuario.name }}
      </li>
    </ul>
  </div>
      <p class="text-lg mb-4">
        Me apasiona la inteligencia artificial, los sistemas distribuidos y la arquitectura de software bien diseñada. Actualmente estoy cursando un bootcamp de IA.
      </p>
      <p class="text-lg">
        Mi objetivo es combinar mis habilidades técnicas con creatividad para construir productos útiles, accesibles y bien estructurados.
      </p>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import api from '../services/axios'

const usuarios = ref([])

onMounted(async () => {
  try {
    const res = await api.get('/users') // ejemplo: GET /api/users
    usuarios.value = res.data
  } catch (err) {
    console.error('Error al cargar usuarios:', err)
  }
})
</script>



