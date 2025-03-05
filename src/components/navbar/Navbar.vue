<script setup>
const links = [
  { id: "home", label: "HOME" },
  { id: "about", label: "SOBRE" },
  { id: "skills", label: "HABILIDADES" },
  { id: "projects", label: "PROJETOS" },
  { id: "contact", label: "CONTATO" },
];
</script>

<template>
  <header id="header" class="fixed-top bg-dark py-3">
    <nav>
      <div class="container">
        <button
            class="navbar-toggler d-lg-none"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarNav"
            aria-controls="navbarNav"
            aria-expanded="false"
            aria-label="Toggle navigation"
        >
          <i class="bi bi-list" style="color: white"></i>
          <span class="ms-2 text-white">Menu</span> <!-- Texto "Menu" ao lado do ícone -->
        </button>
        <ul class="d-none d-lg-flex d-flex justify-content-center list-unstyled p-0 m-0 position-relative flex-wrap">
          <div class="d-flex justify-content-between align-items-center w-100 p-2">
            <template v-for="(link, index) in links" :key="link.id">
              <li class="d-flex align-items-center mb-2 mb-md-0">
                <a :href="'#' + link.id" class="text-decoration-none fw-bold fs-5 text-pink transition">
                  {{ link.label }}
                </a>
              </li>
              <span v-if="index < links.length - 1" class="mx-3 text-pink fs-5 lh-1">
                <strong>|</strong>
              </span>
            </template>
          </div>
        </ul>
      </div>
      <div class="collapse navbar-collapse d-lg-none" id="navbarNav">
        <ul class="navbar-nav">
          <template v-for="link in links" :key="link.id">
            <li class="nav-item">
              <a :href="'#' + link.id" class="nav-link text-pink fw-bold fs-5 transition">
                {{ link.label }}
              </a>
            </li>
          </template>
        </ul>
      </div>
    </nav>
  </header>
</template>

<style scoped>
/* Estilos personalizados que o Bootstrap não cobre */
.text-pink {
  color: #ff4081; /* Cor rosa mais vibrante */
}

.transition {
  transition: all 0.3s ease;
}

.text-pink:hover {
  color: #f06292; /* Alteração na cor ao passar o mouse */
  text-decoration: underline;
}
/* Responsividade */
@media (max-width: 768px) {
  /* Ajustes para o menu colapsável em telas pequenas */
  #header nav ul.navbar-nav {
    flex-direction: column;
    text-align: center;
  }

  #header nav ul.navbar-nav li.nav-item {
    margin: 10px 0; /* Aumenta o espaçamento entre os itens */
  }
}
</style>
