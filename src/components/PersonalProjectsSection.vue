<template>
  <section id="projects" class="personal-projects">
    <h1 class="title">Projetos Pessoais</h1>
    <div class="card-wrapper">
    <div v-for="project in projects" :key="project.id" class="card-projects">
    <div class="infos-container">
        <h1>{{ project.title }}</h1>
        <hr>
        <p>{{ project.description }}</p>
        <div class="d-links">
          <a
          :href="project.link"
          target="_blank"
          rel="noopener noreferrer"
          >Ver projeto</a
          >
          <a :href="project.repo" target="_blank" rel="noopener noreferrer"
          >Ver Repositório</a
          >
        </div>
        <div class="techs-container">
          <span class="badge" v-for="tech in project.techs" :key="tech">{{
            tech
          }}</span>
        </div>
      </div>
    </div>
  </div>
  </section>
</template>

<script>
export default {
  data () {
    return {
      projects: [
        {
          id: 6,
          title: 'Docs Agile',
          link: 'https://agile-docs.netlify.app/',
          repo: 'https://github.com/joao-belmiro/agile-docfy',
          description: 'Projeto criado com o para aprendermais sobre métodologias ágeis do mercado e exercitar o aprendizado com cursos novos, inplantando também a internacionalização e web scrapping',
          techs: ['Vue.js 3', 'web scrapping', 'javaScript', 'Git', 'HTML5', 'SASS', 'vue-i18n']
        },
        {
          id: 5,
          title: 'Dashboard Crm',
          link: 'https://dash-crm.netlify.app/',
          repo: 'https://github.com/joao-belmiro/crm-admin',
          description:
            'Dashboard com formulários e componentes autorais inspirados no material design, possui responsividade e menu lateral funcional',
          techs: ['Vue.js', 'javaScript', 'Git', 'HTML5', 'SASS']
        },
        {
          id: 4,
          title: 'Minha Agenda',
          link: 'https://free-notes.netlify.app',
          repo: 'https://github.com/joao-belmiro/my-notes',
          description:
            'Aplicação para a criação de notas com editor de texto embutido com salvamento de dados locais com indexeddb',
          techs: ['Vue.js', 'javaScript', 'Git', 'HTML5', 'SASS', 'indexeddb']
        },
        {
          id: 3,
          title: 'Crud Vue e Firebase',
          link: 'https://crud-vue-firebase.netlify.app/',
          repo: 'https://github.com/joao-belmiro/frontend-test',
          description:
            'Crud simples de uma única entidade utilizando o firebase como banco dedados NOSQL, possui responsividade para dispositivos móveis, sendo hospedado na netlify',
          techs: ['Vue.js', 'javaScript', 'Git', 'HTML5', 'SASS']
        },
        {
          id: 2,
          title: 'Seu Fipe',
          link: 'https://fipe-search.netlify.app/',
          repo: 'https://github.com/joao-belmiro/fipe-search',
          description:
            'Front-end desenvolvido com base em uma api aberta encontrada https://publicapis.dev/, nesta aplicação é feita a busca do valor de um veículo seja carro, motocicleta ou caminhão ,também é mostrado um gráfico com o histórico dos 3 últimos valores coletados, foi disponibilizado na netlify',
          techs: ['Nuxt.js', 'HTML5', 'CSS3', 'javaScript', 'Axios']
        },
        {
          id: 1,
          title: 'Buscador de Letras',
          link: 'https://joao-belmiro.github.io/lyrics-search/',
          repo: 'https://github.com/joao-belmiro/lyrics-search',
          description:
            'Aplicação feita para buscar letras de musicas com base em uma api aberta , a aplicação foi desenvolvida a partir do video https://www.youtube.com/watch?v=sgiTuXGin2I, com o intuito de estudar javaScript puro, foram feitas algumas adições em relação a aplicação feita no video, agora ela aprenta o preview da musica, imagem da capa e o nome do albúm.',
          techs: ['javaScript', 'HTML5', 'CSS3']
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.personal-projects {
  padding-bottom: 32px;
  display: flex;
  flex-direction: column;
  row-gap: 32px;
  justify-content: flex-start;
  align-items: center;
  @media (max-width: 999px) {
    margin: 0 16px;
    align-items: flex-start;
  }
  .title {
    width: 80%;
    box-sizing: border-box;
    border-left: 10px solid $primary ;
    padding-left: 16px;
  }
  h1 {
    font-size: 32px;
    @media (max-width: 999px) {
        font-size: 22px;
    }
  }
  .card-wrapper {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: flex-start;
    flex-wrap: wrap;
    column-gap: 16px;
  }
  .card-projects {
    width: 39.2%;
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    border-radius: 4px;
    border: 1px solid $grey-1;
    height: 335px;
    box-shadow: 4px 4px 0px -1px rgba(153, 153, 153, .8);
    margin-bottom: 16px;
    @media (max-width: 999px) {
      width: 100%;
      flex-direction: column;
      height: auto;
    }
    .infos-container {
      padding: 16px;
      h1 {
        color: $primary;
        letter-spacing: 3px;
        text-transform: uppercase;
        font-weight: 700;
        opacity: 0.8;
        margin-bottom: 16px;
        line-height: 1em;
        @media (max-width: 999px) {
          font-size: 22px;
        }
      }

      p {
        margin:16px 0;
        font-size: 14px;
        text-align: justify;
        @media (max-width: 999px) {
          font-size: 12px;
          letter-spacing: 1px;
          text-align: none;
        }
      }
      .d-links {
        display: flex;
        flex-direction: row;
        gap: 16px;
        justify-content: flex-start;
        align-items: center;
      }
      a {
        text-decoration: none;
        color: $primary;
        font-size: 14px;
        text-transform: uppercase;
        letter-spacing: 2px;
        font-weight: 600;
        padding: 8px;
          border: 1px solid $primary;
          border-radius: 6px;
        &:hover {
          opacity: 0.7;
        }
        @media (max-width: 999px) {
          font-size: 10px;
        }
      }
    }
    .techs-container {
      margin-top: 32px;
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      column-gap: 10px;
      row-gap: 10px;

      .badge {
        font-size: 10px;
        font-weight: 550;
        letter-spacing: 1px;
        line-height: 24px;
        border-radius: 15px;
        padding: 0 12px;
        background: $secondary;
        color: #fff;
      }
    }
  }
}
</style>
