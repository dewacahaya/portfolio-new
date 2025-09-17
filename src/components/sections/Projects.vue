<script setup>
import { ref, computed } from 'vue'

// kategori tab
const categories = [
  { id: 'all', name: 'All' },
  { id: 'campus', name: 'Campus' },
  { id: 'personal', name: 'Personal' },
  { id: 'others', name: 'Others' },
]

// project list
const projects = ref([
  { id: 1, title: 'Web-based Balinese Traditional Clothing Sales', desc: 'Final Exam Project with Laravel + MySQL', link: 'https://github.com/dewacahaya/sri-ratih-collections.git', category: 'campus', image: 'https://cdn.discordapp.com/attachments/911837926063743028/1416978697696841748/image.png?ex=68c8cfbf&is=68c77e3f&hm=a7cb56e1735f7d9a3e89b5fb3ac0d6820d3fb4b045b71dcc75bd016cc0b04a5c&' },
  { id: 2, title: 'Portfolio Website', desc: 'Personal Portfolio Web with VueJS & Tailwindcss', link: 'https://decay-portfolio-new.vercel.app/', category: 'personal', image: 'https://cdn.discordapp.com/attachments/911837926063743028/1417724480901615757/image.png?ex=68cb8650&is=68ca34d0&hm=aa4812f23655a604ea539d7b3b9f09018f2dfe9269510ea01993de056f818f54&' },
  { id: 3, title: 'Resto Web', desc: 'CRUD Resto Web Application using Laravel', link: 'https://github.com/dewacahaya/crud-resto-admin.git', category: 'personal', image: 'https://cdn.discordapp.com/attachments/911837926063743028/1416981143827251313/image.png?ex=68c8d206&is=68c78086&hm=0a73deb8addfe97bb13019ffabd0c358f622aa3a6c35c46db724099db817f736&' },
  { id: 4, title: 'Organization Monitoring App Design', desc: 'Organization Monitoring Mobile App Design for Mid-tern Test ', link: 'https://www.figma.com/design/rK9dSsI4Qa0yQpFHsma6ET/HCI-UTS?node-id=0-1&t=SXIpCSsmapREgr18-1', category: 'campus', image: 'https://cdn.discordapp.com/attachments/911837926063743028/1417009378812362866/image.png?ex=68c8ec52&is=68c79ad2&hm=72ac917440b8ad5915b99e6cece074a22106b619af356c32303e81c13965c67c&' },
  { id: 5, title: 'Social Media Design', desc: 'Designing Social Media Design for Committee', link: '', category: 'campus', image: 'https://cdn.discordapp.com/attachments/911837926063743028/1416976259644264458/image.png?ex=68c8cd7a&is=68c77bfa&hm=015acbcd4753cae925bc2b1bf1375a3c94ebc0b14751f3ad9ba795b2e10bd2cb&' },
  { id: 6, title: 'DompetKita - Mobile App Design', desc: 'Finance App Design for INTECHFEST Competition 2025', link: 'https://www.figma.com/design/PjdfF91gqlCDejVVHLmAe8/PNBDC-2025?node-id=0-1&t=KEal8CqwZhVrAt03-1', category: 'others', image: 'https://cdn.discordapp.com/attachments/911837926063743028/1417009808204103801/image.png?ex=68c8ecb9&is=68c79b39&hm=ba5b17c328a76ae329e038f1cd0f887742e1893054f8e549ff5430c89e2e33b7&' },
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
