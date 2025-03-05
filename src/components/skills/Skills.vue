<template>
  <section id="skills" class="container-skills text-center py-5 mt-5">
    <h2 class="fw-bold mb-5" style="color: #ff4081;">Habilidades</h2>
    <div class="skills-container d-flex justify-content-center flex-wrap gap-4">
      <div class="skill d-flex flex-column align-items-center">
        <img src="../../assets/excel-icon.png" alt="Ícone Excel" class="skill-icon mb-3">
        <p class="mb-0 text-light">Excel</p>
      </div>
      <!-- Repetir para outras habilidades -->
      <div class="skill d-flex flex-column align-items-center">
        <img src="../../assets/powerbi-icon.png" alt="Ícone Power BI" class="skill-icon mb-3">
        <p class="mb-0 text-light">Power BI</p>
      </div>
      <div class="skill d-flex flex-column align-items-center">
        <img src="../../assets/python-icon.png" alt="Ícone Python" class="skill-icon mb-3">
        <p class="mb-0 text-light">Python</p>
      </div>
      <div class="skill d-flex flex-column align-items-center">
        <img src="../../assets/sql-icon.png" alt="Ícone SQL" class="skill-icon mb-3">
        <p class="mb-0 text-light">SQL</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Skills'
}
</script>

<style scoped>
/* Estilos personalizados que o Bootstrap não cobre */
.container-skills {
  padding: 60px 0; /* Espaçamento interno */
}

.skill-icon {
  width: 80px; /* Tamanho da imagem */
  height: 80px;
  object-fit: contain; /* Garante que a imagem mantenha a proporção */
}
</style>