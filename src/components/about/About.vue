<template>
  <section id="about" class="container py-5">
    <div class="row align-items-center mt-5">
      <!-- Imagem de perfil -->
      <div class="col-md-4 text-center">
        <img src="../../assets/maraysa-perfil.jpg" alt="Foto de Maraysa Macedo, Analista de Dados Júnior" class="img-fluid rounded-circle shadow-lg" style="border: #ff4081 solid 3px" aria-label="Foto de Maraysa Macedo, Analista de Dados Júnior">
      </div>

      <div class="col-md-8">
        <h2 class="fw-bold" style="color: #ff4081;">Sobre Mim - Analista de Dados Júnior</h2>
        <p class="text-light">
          Sou uma pessoa apaixonada pela resolução de problemas, o que me levou a conhecer a área de Dados. Embora não atue diretamente na área de tecnologia no momento, já tive experiência como Analista de Sistema Júnior em <strong>C#, .NET, ASP.NET Core e JavaScript</strong>. Durante esse período, aprendi a lidar com desafios técnicos e a desenvolver soluções práticas que facilitaram processos e otimizaram resultados.
        </p>
        <p class="text-light">
          Minha paixão por dados me motivou a explorar o vasto campo da análise e, atualmente, estou em um <strong>curso técnico de Análise de Dados</strong> para aprofundar meus conhecimentos e expandir minhas habilidades. Meu maior objetivo é entregar soluções baseadas em dados que não apenas otimizem processos, mas também proporcionem resultados reais e eficientes.
        </p>
        <p class="text-light">
          Tenho uma forte capacidade analítica e atenção aos detalhes, o que me permite identificar padrões e conexões nos dados de forma eficaz. Acredito também que a comunicação é um aspecto fundamental, pois é essencial transformar dados em insights claros e acessíveis para todos os envolvidos na tomada de decisão.
        </p>
        
        <!-- Lista de habilidades com ênfase em palavras-chave SEO -->
        <ul class="text-light">
          <li><strong>Ferramentas de Análise de Dados:</strong> Python, SQL</li>
          <li><strong>Experiência em Banco de Dados:</strong> SQL Server, MySQL</li>
          <li><strong>Visualização de Dados:</strong> Power BI</li>
          <li><strong>Desenvolvimento e Processamento de Dados:</strong> Python, Pandas, NumPy</li>
        </ul>

        <!-- Link para contato ou portfólio -->
        <p class="text-light">
          <a href="#portfolio" class="text-decoration-none" style="color: #ff4081;"></a>
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'About'
}
</script>

<style scoped>
.img-fluid {
  max-width: 250px;
}
</style>
