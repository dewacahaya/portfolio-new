<script setup>

</script>

<template>
  <section id="about" class="min-h-screen flex flex-col md:flex-row justify-center items-center
           text-center md:text-left px-6 py-12 bg-white dark:bg-gray-800">

    <!-- Image -->
    <div class="hidden mb-8 md:flex md:justify-center md:mr-4 md:mb-0 md:w-1/2">
      <img src="@/assets/images/foto1.png" alt="Decay"
        class="w-56 h-60 md:w-96 md:mt-5 md:h-1/2 object-cover shadow-2xl border-4 border-green-500 dark:border-green-300 rounded-full" />
    </div>

    <!-- Text -->
    <div class="flex flex-col items-center md:items-start md:w-1/2 md:mr-8 space-y-6">
      <h1 class="text-4xl md:text-5xl font-bold text-gray-800 leading-tight dark:text-white">
        Who is me?
      </h1>

      <h3 class="text-lg md:text-xl font-semibold text-black px-2 dark:text-white">
        I'm <span class="font-bold">I Dewa Gede Cahaya Darma Putra</span>, a Computer Science student at the Indonesian
        Institute of Business and Technology (INSTIKI). Interested in web development, particularly front-end
        development. Proficient in JavaScript and PHP programming languages, as well as the Laravel and VueJS
        frameworks. Although I am a Computer Science student interested in web development, I also have an interest in
        design and the creative world, such as UI/UX design, graphic design, and so on.
      </h3>

      <div class="flex space-x-4 mt-2">
        <a href="https://www.instagram.com/dewacahaya._/" target="_blank" rel="noopener noreferrer"
          class=" px-6 py-3 rounded-full shadow-lg hover:bg-green-300 hover:translate-y-2 transition duration-300 dark:bg-white">
          <img
            src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Instagram_icon.png/1200px-Instagram_icon.png"
            alt="Instagram" class="w-10 h-10 inline-block">
        </a>
        <a href="https://github.com/dewacahaya/" target="_blank" rel="noopener noreferrer"
          class=" px-6 py-3 rounded-full shadow-lg hover:bg-green-300 hover:translate-y-2 transition duration-300 dark:bg-white">
          <img
            src="https://cdn.discordapp.com/attachments/911837926063743028/1416607701038923816/image.png?ex=68c7763b&is=68c624bb&hm=b51154db853d93c70f3ce8863dc9c1deafffe35cd25ed3234c114a132aea55c5&"
            alt="GitHub" class="w-10 h-10 inline-block">
        </a>
        <!-- <a href="https://www.instagram.com/dewacahaya._/" target="_blank" rel="noopener noreferrer"
          class=" px-6 py-3 rounded-full shadow-lg hover:bg-white hover:translate-y-2 transition duration-300">
          <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Instagram_icon.png/1200px-Instagram_icon.png" alt="Instagram" class="w-10 h-10 inline-block">
        </a> -->
      </div>
    </div>

  </section>
</template>

<style scoped>
.custom-shape-divider-top-1757816295 {
  top: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
}
</style>
