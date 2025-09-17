<script setup>

</script>

<template>
  <section id="hero" class="min-h-screen flex flex-col-reverse md:flex-row justify-center items-center
           text-center md:text-left px-6 py-12 bg-gradient-to-b from-white to-green-300 dark:from-green-800 dark:to-gray-800">

    <!-- Text -->
    <div class="flex flex-col items-center md:items-start md:w-1/2 space-y-6 lg:ml-28">
      <h1 class="text-4xl md:text-5xl font-bold text-gray-800 leading-tight dark:text-white">
        Dewa <br> Cahaya /
        <span class="bg-green-600 px-3 py-1 md:px-4 md:py-2 text-white shadow-xl rounded-2xl inline-block">
          Decay
        </span>
      </h1>

      <h3 class="text-lg md:text-xl font-semibold text-black bg-white/70 px-4 py-2 rounded-xl shadow-sm dark:bg-green-600 dark:text-white">
        UI/UX Designer | Web Developer | Gamer
      </h3>

      <div class="flex space-x-4">
        <!-- <a href="#projects"
          class="bg-green-600 text-white px-6 py-3 rounded-full shadow-lg hover:bg-green-700 transition duration-300">
          See My Works
        </a>
        <a href="#contact"
          class="bg-green-600 text-white px-6 py-3 rounded-full shadow-lg hover:bg-green-700 transition duration-300">
          Let's Connect
        </a> -->

        <a href="#projects" class="box">See My Works</a>
        <a href="#footer" class="box">
          Let's Connect
        </a>
      </div>
    </div>

    <!-- Image -->
    <div class="flex justify-center mb-8 md:mb-0 md:w-1/2 relative group">
      <!-- Background Image (second) -->
      <img src="@/assets/images/foto2.png" alt="Decay Alt"
        class="absolute top-0 left-0 w-56 h-60 md:w-80 md:h-80 mt-14 object-cover shadow-xl border-4 border-black dark:border-white rounded-full opacity-0 group-hover:opacity-100 group-hover:-translate-x-6 transition-all duration-500 ease-in-out" />

      <!-- Foreground Image (main) -->
      <img src="@/assets/images/foto1.png" alt="Decay"
        class="relative w-56 h-60 md:w-80 md:h-80 object-cover shadow-2xl border-4 border-black dark:border-white rounded-full transition-all duration-500 ease-in-out group-hover:translate-x-6" />
    </div>
  </section>
</template>

<style scoped>
/* From Uiverse.io by Cornerstone-04 */
.box {
  /* width: 140px; */
  height: auto;
  float: left;
  transition: .5s linear;
  position: relative;
  display: flex;
  overflow: hidden;
  padding: 15px;
  text-align: center;
  margin: 0 5px;
  background: rgb(14, 186, 14);
  color: white;
  text-transform: uppercase;
  font-weight: bold;
  border-radius: 30px;
}

.box:before {
  position: absolute;
  content: '';
  left: 0;
  bottom: 0;
  height: 4px;
  width: 100%;
  border-bottom: 4px solid transparent;
  border-left: 4px solid transparent;
  border-radius: 30px;
  box-sizing: border-box;
  transform: translateX(100%);
}

.box:after {
  position: absolute;
  content: '';
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  border-top: 4px solid transparent;
  border-right: 4px solid transparent;
  border-radius: 30px;
  box-sizing: border-box;
  transform: translateX(-100%);
}

.box:hover {
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
}

.box:hover:before {
  border-color: #00ff9d;
  height: 100%;
  border-radius: 30px;
  transform: translateX(0);
  transition: .3s transform linear, .3s height linear .3s;
}

.box:hover:after {
  border-color: #00ff9d;
  height: 100%;
  border-radius: 30px;
  transform: translateX(0);
  transition: .3s transform linear, .3s height linear .5s;
}

button {
  color: black;
  text-decoration: none;
  cursor: pointer;
  outline: none;
  border: none;
  background: transparent;
}
</style>
