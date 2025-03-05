<script setup>
import Header from './header/Header.vue';
import About from "./about/About.vue";
import Skills from "./skills/Skills.vue";
import Projects from "./projects/Projects.vue";
import Footer from "./footer/Footer.vue";


</script>

<template>
  <div class="app">
    <Header/>
    <About/>
    <skills/>
    <Projects />
    <Footer />
  </div>
</template>

<style scoped>

.app {
  background-color: #1d1d1d;
}

</style>
