<template>
  <footer class="bg-dark text-white py-3 mt-5">
    <section id="contact" class="container d-flex flex-column flex-md-row justify-content-between align-items-center">

      <!-- Bloco de contato -->
      <div class="text-center d-flex flex-column align-items-center w-100 w-md-75 mb-3 mb-md-0">
        <p class="mb-3">FALE COMIGO!</p>
        <div class="d-grid col-8 col-md-6 mx-auto">
          <button type="button" class="btn btn-pink" @click="sendEmail">Enviar e-mail</button>
        </div>
      </div>

      <!-- Ícones sociais -->
      <div class="social-icons d-flex gap-3 justify-content-center justify-content-md-end w-md-25" >
        <a href="https://github.com/maraysamacedo" target="_blank" class="bi bi-github text-white fs-3"></a>
        <a href="https://www.linkedin.com/in/maraysamacedo/" target="_blank" class="bi bi-linkedin text-white fs-3"></a>
      </div>

    </section>
  </footer>
</template>

<style scoped>
.btn-pink {
  background-color: #ff4081;
  color: white;
  border-radius: 5px;
}

.btn-pink:hover {
  background-color: #e60073;
}

@media (max-width: 768px) {
  /* Ajuste para telas menores */
  .text-center p {
    font-size: 1.5rem; /* Tamanho de texto ajustado em telas menores */
  }

  .social-icons {
    justify-content: center; /* Garante que os ícones fiquem centralizados em telas pequenas */
  }
}

@media (max-width: 576px) {
  /* Ajuste para telas ainda menores */
  .text-center p {
    font-size: 1.2rem; /* Ajuste de tamanho da fonte para telas muito pequenas */
  }

  .social-icons a {
    font-size: 2rem; /* Ícones sociais menores em telas muito pequenas */
  }
}
</style>

<script>
export default {
  methods: {
    sendEmail() {
      window.location.href = 'mailto:maraysa.macedo@outlook.com.br?subject=Assunto%20do%20e-mail&body=Corpo%20do%20e-mail';
    }
  }
}
</script>
