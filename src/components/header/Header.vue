<template>
  <Navbar />
  <header class="hero d-flex align-items-center">
    <div id="home" class="container-fluid h-100 d-flex flex-column justify-content-center align-items-center text-center">
      <h1>
        <span class="hello text-uppercase fw-light fs-3 mb-3">OLÁ, SEJA BEM VINDO.</span>
      </h1>
      <h2>
        <span class="name fw-bold fs-1">Eu sou</span>
      </h2>
      <h2>
        <span class="name fw-bold fs-1">Maraysa Macedo</span>
      </h2>
      <p class="profession text-uppercase fs-5 mt-3">| Analista de Dados |</p>
      <a href="#about" class="btn btn-outline-pink rounded-pill px-4 py-2 mt-4">Saiba Mais</a>
    </div>
  </header>
</template>

<script>
import { defineComponent } from "vue";
import Navbar from "../navbar/Navbar.vue";

export default defineComponent({
  components: { Navbar }
});
</script>

<style scoped>
/* Estilos personalizados que o Bootstrap não cobre */
.hero {
  background: linear-gradient(to right, #1d1d1d, #333);
  height: 95vh;
}

.hello {
  color: #f17ea1; /* Cor rosa bebê */
}

.name {
  color: #fff; /* Cor branca */
}

.profession {
  color: #fff;
}

.btn-outline-pink {
  border: 2px solid #ff4081; /* Cor rosa vibrante */
  color: #ff4081; /* Cor rosa vibrante */
  font-weight: bold;
  text-transform: uppercase;
  transition: all 0.3s ease;
}

.btn-outline-pink:hover {
  background-color: #ff4081;
  color: #fff;
}
</style>