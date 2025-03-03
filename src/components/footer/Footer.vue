<template>
  <footer class="bg-dark text-white py-3 mt-5">
    <section id="contact" class="container d-flex justify-content-between align-items-center">

      <div class="text-center d-flex flex-column align-items-center w-75">
        <p class="mb-3" style="margin-left: 350px">FALE COMIGO!</p>
        <div class="d-grid col-6" style="margin-left: 350px">
          <button type="button" class="btn btn-pink" @click="sendEmail">Enviar e-mail</button>
        </div>
      </div>

      <div class="social-icons d-flex gap-3 justify-content-end w-25">
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
