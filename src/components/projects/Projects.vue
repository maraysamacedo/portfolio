<template>
  <section id="projects" class="container-skills text-center py-5 mt-5">
    <h2 class="fw-bold mb-5" style="color: #ff4081;">Projetos</h2>
    <div id="carouselExampleIndicators" class="carousel slide">
      <!-- Indicadores do Carousel -->
      <div class="carousel-indicators">
        <button
            v-for="(group, index) in groupedCards"
            :key="index"
            type="button"
            data-bs-target="#carouselExampleIndicators"
            :data-bs-slide-to="index"
            :class="{ active: index === 0 }"
            :aria-label="'Slide ' + (index + 1)"
        ></button>
      </div>

      <!-- Slides do Carousel -->
      <div class="carousel-inner">
        <div
            v-for="(group, index) in groupedCards"
            :key="index"
            :class="['carousel-item', { active: index === 0 }]"
        >
          <div class="d-flex justify-content-center gap-4 mb-5 flex-wrap">
            <div
                v-for="(card, cardIndex) in group"
                :key="cardIndex"
                class="card"
                style="width: 18rem;"
            >
              <img :src="card.src" class="card-img-top" :alt="card.alt"/>
              <div class="card-body">
                <h5 class="card-title">{{ card.title }}</h5>
                <p class="card-text">{{ card.description }}</p>
                <a :href="card.link" class="btn btn-primary">Ver Projeto</a>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Controles do Carousel -->
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Anterior</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Próximo</span>
      </button>
    </div>
  </section>
</template>

<script setup>
import { onMounted, ref, computed, onUnmounted } from 'vue';
import 'bootstrap/dist/css/bootstrap.min.css';
import { Carousel } from 'bootstrap';

// Array de cards com informações
const cards = ref([
  {
    src: new URL('../../assets/Projeto_Integração_POWERBI_SQL.gif', import.meta.url).href,
    alt: 'Imagem 1',
    title: 'Projeto de Análise de Vendas utilizando SQL e Power BI',
    description: 'Integração de dados de vendas, produtos, clientes e geografia para visualizações interativas. Inclui criação de view para análise de vendas e atualização de dados na tabela de vendas.',
    link: 'https://github.com/maraysamacedo/analisedevendas',
  },
  {
    src: new URL('../../assets/img projeto python IA.png', import.meta.url).href,
    alt: 'Imagem 2',
    title: 'Previsão de Score com IA',
    description: 'Aplica técnicas de Inteligência Artificial para prever o score de crédito de clientes, utilizando algoritmos de aprendizado de máquina, como os da biblioteca Scikit-learn. O modelo é treinado e testado usando dados históricos, com análise e manipulação de dados realizada em Pandas.',
    link: 'https://github.com/maraysamacedo/previsaoscoreIA',
  },
  {
    src: new URL('../../assets/Projeto POWER BI  Dashboard Finanças.gif', import.meta.url).href,
    alt: 'Imagem 3',
    title: 'Dashboard Finanças',
    description: 'Dashboard de análises financeiras, integrando dados de receitas, despesas e KPIS para visualização interativa. Permite o acompanhamento em tempo real da saúde financeira de uma organização, oferecendo insights valiosos para tomada de decisão.',
    link: 'https://github.com/maraysamacedo/dashfinancas',
  },
  {
    src: new URL('../../assets/Cadastro automatizado.png', import.meta.url).href,
    alt: 'Imagem 4',
    title: 'Cadastro de Produtos Automatizado',
    description: 'Este projeto automatiza o cadastro de produtos em um sistema web usando PyAutoGUI para simular interações e pandas para ler dados de um CSV. O script realiza o login e preenche o formulário de cadastro de forma automatizada. Basta executar o código e o processo de cadastro será concluído automaticamente.',
    link: 'https://github.com/maraysamacedo/cadastroautomatizado',
  },
  {
    src: new URL('../../assets/Projeto POWER BI  Dashboard DRE.gif', import.meta.url).href,
    alt: 'Imagem 5',
    title: 'Projeto 5',
    description: 'Projeto em Power BI para visualização interativa do DRE, permitindo análise detalhada de receitas, despesas e lucros para facilitar decisões financeiras. Utiliza DAX para cálculos dinâmicos e Power Query para transformação e limpeza de dados.',
    link: 'https://github.com/maraysamacedo/dashboarddre',
  },
  {
    src: new URL('../../assets/Projeto POWER BI  Dashboard Projetos.gif', import.meta.url).href,
    alt: 'Imagem 6',
    title: 'Dashboard Projetos',
    description: 'Oferece uma análise interativa de dados de gestão de projetos, com foco em monitorar progresso, status e desempenho de iniciativas, utilizando KPIs para facilitar a tomada de decisões estratégicas.',
    link: 'https://github.com/maraysamacedo/dashboardprojetos',
  },
  {
    src: new URL('../../assets/Projeto POWER BI  Dashboard RH.gif', import.meta.url).href,
    alt: 'Imagem 7',
    title: 'Dashboard RH',
    description: 'Oferece visualizações interativas de dados de recursos humanos, incluindo análise de desempenho, cargos, dados demográficos e KPIs, visando facilitar decisões estratégicas na gestão de pessoas.',
    link: 'https://github.com/maraysamacedo/dashboardrh/',
  },
  {
    src: new URL('../../assets/Projeto Integração EXCEL e SQ.png', import.meta.url).href,
    alt: 'Imagem 8',
    title: 'Projeto de Resultados integrando Excel e SQL',
    description: 'Automatização da importação de dados de arquivos Excel para bancos de dados SQL Server. Permite ler dados de planilhas Excel e inseri-los diretamente nas tabelas do banco de dados. O objetivo é facilitar a integração e migração de dados de forma eficiente e sem a necessidade de processos manuais.',
    link: 'https://github.com/maraysamacedo/integracaoexcelsql',
  },
]);

// Detecta o tamanho da tela e ajusta o número de cards por grupo
const cardsPerGroup = ref(4); // Padrão: 4 cards por slide

const updateCardsPerGroup = () => {
  if (window.innerWidth <= 768) { // Telas pequenas (mobile)
    cardsPerGroup.value = 1;
  } else { // Telas maiores
    cardsPerGroup.value = 4;
  }
};

// Agrupa os cards com base no tamanho da tela
const groupedCards = computed(() => {
  const groups = [];
  for (let i = 0; i < cards.value.length; i += cardsPerGroup.value) {
    groups.push(cards.value.slice(i, i + cardsPerGroup.value));
  }
  return groups;
});

// Inicializa o carrossel e atualiza o agrupamento ao redimensionar
onMounted(() => {
  updateCardsPerGroup(); // Define o número inicial de cards por grupo
  const carouselElement = document.getElementById('carouselExampleIndicators');
  if (carouselElement) {
    new Carousel(carouselElement, {
      interval: 3000,
      wrap: true,
    });
  }

  // Adiciona listener para redimensionamento da tela
  window.addEventListener('resize', updateCardsPerGroup);
});

// Remove o listener ao desmontar o componente (opcional, boa prática)
onUnmounted(() => {
  window.removeEventListener('resize', updateCardsPerGroup);
});
</script>

<style scoped>
.container-skills {
  padding: 60px 0;
}

.carousel-item {
  padding: 20px;
}

.card {
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  width: 18rem; /* Tamanho padrão do card */
}

.card-img-top {
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  height: 200px;
  object-fit: cover;
}

.card-body {
  padding: 20px;
}

.btn-primary {
  background-color: #ff4081;
  border: none;
  transition: background-color 0.3s ease;
}

.btn-primary:hover {
  background-color: #e91e63;
}

/* Media Queries para responsividade */
@media (max-width: 768px) {
  .carousel-item .d-flex {
    flex-direction: column; /* Empilha os cards verticalmente */
    align-items: center; /* Centraliza os cards */
  }

  .card {
    width: 100%; /* O card ocupa toda a largura disponível */
    max-width: 18rem; /* Mantém um limite máximo para o card */
    margin-bottom: 20px; /* Espaçamento entre cards empilhados */
  }

  .carousel-control-prev,
  .carousel-control-next {
    display: block; /* Garante que os controles sejam visíveis em mobile */
  }
}

@media (min-width: 769px) {
  .carousel-item .d-flex {
    flex-direction: row; /* Mantém os cards lado a lado em telas grandes */
  }
}
</style>