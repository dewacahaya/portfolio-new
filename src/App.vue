<script setup>
import Navbar from './components/Navbar.vue'
import Footer from './components/Footer.vue'
import Hero from './components/sections/Hero.vue';
import About from './components/sections/About.vue';
import Tech from './components/sections/Tech.vue';
import Project from './components/sections/Projects.vue';
</script>

<template>
 <div class="flex flex-col min-h-screen">
    <Navbar />
    <main class="flex-1">
      <section id="hero" class="scroll-mt-24"><Hero/></section>
      <section id="about"><About/></section>
      <section id="tech"><Tech/></section>
      <section id="projects" class="scroll-mt-24"><Project/></section>
    </main>
    <section id="footer"><Footer /></section>
  </div>
</template>

<style>
html {
  scroll-behavior: smooth;
}
</style>
