<script setup>
import { ref, computed } from 'vue'

// kategori tab
const categories = [
  { id: 'all', name: 'All' },
  { id: 'campus', name: 'Campus' },
  { id: 'personal', name: 'Personal' },
  { id: 'others', name: 'Others' },
]

import sriratih from '@/assets/images/sriratih.webp'
import portfolio from '@/assets/images/portfolio.webp'
import resto from '@/assets/images/resto.webp'
import hci from '@/assets/images/hci.webp'
import techfest from '@/assets/images/techfest.webp'
import dompetkita from '@/assets/images/dompetkita.webp'

// project list
const projects = ref([
  { id: 1, title: 'Web-based Balinese Traditional Clothing Sales', desc: 'Final Exam Project with Laravel + MySQL', link: 'https://github.com/dewacahaya/sri-ratih-collections.git', category: 'campus', image: sriratih },
  { id: 2, title: 'Portfolio Website', desc: 'Personal Portfolio Web with VueJS & Tailwindcss', link: 'https://decay-portfolio-new.vercel.app/', category: 'personal', image: portfolio },
  { id: 3, title: 'Resto Web', desc: 'CRUD Resto Web Application using Laravel', link: 'https://github.com/dewacahaya/crud-resto-admin.git', category: 'personal', image: resto },
  { id: 4, title: 'Organization Monitoring App Design', desc: 'Organization Monitoring Mobile App Design for Mid-tern Test ', link: 'https://www.figma.com/design/rK9dSsI4Qa0yQpFHsma6ET/HCI-UTS?node-id=0-1&t=SXIpCSsmapREgr18-1', category: 'campus', image: hci },
  { id: 5, title: 'Social Media Design', desc: 'Designing Social Media Design for Committee', link: '', category: 'campus', image: techfest },
  { id: 6, title: 'DompetKita - Mobile App Design', desc: 'Finance App Design for INTECHFEST Competition 2025', link: 'https://www.figma.com/design/PjdfF91gqlCDejVVHLmAe8/PNBDC-2025?node-id=0-1&t=KEal8CqwZhVrAt03-1', category: 'others', image: dompetkita },
])

// state aktif
const activeCategory = ref('all')

// filter project
const filteredProjects = computed(() => {
  if (activeCategory.value === 'all') return projects.value
  return projects.value.filter(p => p.category === activeCategory.value)
})
</script>

<template>
  <section id="projects" class="min-h-screen flex flex-col md:flex-col md:justify-start md:items-start
           text-center md:text-left px-6 py-12 bg-white dark:bg-gray-800">
    <div class="container mx-auto px-6">
      <!-- Title -->
      <h2 class="text-3xl md:text-4xl font-bold text-center text-black mb-8 dark:text-white">My Projects</h2>

      <!-- Filter Tabs -->
      <div class="flex justify-center space-x-6 mb-12">
        <button v-for="cat in categories" :key="cat.id" @click="activeCategory = cat.id"
          class="text-lg font-medium transition duration-300" :class="activeCategory === cat.id
            ? 'text-green-400 border-b-2 border-green-600 pb-1'
            : 'text-gray-600 hover:text-green-600 dark:text-white'">
          {{ cat.name }}
        </button>
      </div>

      <!-- Projects Grid -->
      <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
        <div v-for="proj in filteredProjects" :key="proj.id"
          class="bg-white shadow-md rounded-xl overflow-hidden hover:shadow-xl transition duration-300 dark:bg-gray-700 dark:hover:shadow-white/40">
          <div class="bg-gray-300 h-40 flex items-center justify-center">
            <!-- pakai gambar asli -->
            <img v-if="proj.image" :src="proj.image" :alt="proj.title" class="h-full w-full object-cover" />
            <span v-else class="text-gray-500">No Image</span>
          </div>
          <div class="p-4 text-left flex flex-col justify-between">
            <h3 class="text-lg text-black font-bold dark:text-white">{{ proj.title }}</h3>
            <p class="text-gray-600 text-sm mb-4 dark:text-gray-200">{{ proj.desc }}</p>
            <a v-if="proj.link" :href="proj.link" target="_blank" rel="noopener noreferrer" class="text-green-600 font-medium flex items-end space-x-1 hover:underline dark:text-green-300">
              <span>View more</span>
              <span>→</span>
            </a>
          </div>
        </div>
      </div>
      <p class="text-black text-center font-semibold mt-8 dark:text-white">And Many More...</p>
    </div>
  </section>
</template>

<style scoped></style>
