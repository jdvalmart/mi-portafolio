<template>
  <section class="min-h-screen bg-gray-100 px-6 py-12">
    <div class="max-w-6xl mx-auto">
      <h2 class="text-3xl md:text-4xl font-bold mb-10 text-center">Mis Proyectos</h2>

      <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
        <ProjectCard
          v-for="(project, index) in projects"
          :key="index"
          :title="project.title"
          :description="project.description"
          :technologies="project.technologies"
          :link="project.link"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import ProjectCard from '../components/ProjectCard.vue'

const projects = [
  {
    title: 'Match Color Game',
    description: 'Juego de memoria visual multiplataforma desarrollado con Ionic.',
    technologies: ['Ionic', 'TypeScript', 'Capacitor'],
    link: 'https://github.com/tuusuario/match-color',
  },
  {
    title: 'KnowFinances App',
    description: 'Aplicación de finanzas personales construida en Vue + Laravel.',
    technologies: ['Vue', 'Laravel', 'Tailwind'],
    link: 'https://github.com/tuusuario/knowfinances',
  },
  // Agrega más proyectos aquí
]
</script>
