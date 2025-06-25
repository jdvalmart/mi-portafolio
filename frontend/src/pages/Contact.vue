<template>
  <section class="min-h-screen bg-white px-6 py-12">
    <div class="max-w-xl mx-auto">
      <h2 class="text-3xl md:text-4xl font-bold mb-6 text-center">Contáctame</h2>

      <form @submit.prevent="handleSubmit" class="space-y-4">
        <input v-model="form.name" type="text" placeholder="Tu nombre" class="w-full px-4 py-3 border rounded-lg" required />
        <input v-model="form.email" type="email" placeholder="Tu correo" class="w-full px-4 py-3 border rounded-lg" required />
        <textarea v-model="form.message" rows="5" placeholder="Mensaje" class="w-full px-4 py-3 border rounded-lg" required></textarea>
        <button type="submit" class="w-full py-3 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition">Enviar</button>
      </form>

      <p v-if="successMessage" class="text-green-600 mt-4 text-center">{{ successMessage }}</p>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import axios from 'axios'

const form = ref({
  name: '',
  email: '',
  message: '',
})
const successMessage = ref('')

const handleSubmit = async () => {
  try {
    await axios.post('https://tu-backend.com/api/contact', form.value)
    successMessage.value = '¡Mensaje enviado con éxito!'
    form.value = { name: '', email: '', message: '' }
  } catch (err) {
    alert('Hubo un error al enviar el mensaje.')
  }
}
</script>
