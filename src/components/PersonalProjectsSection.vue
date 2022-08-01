<template>
  <section id="projects" class="personal-projects">
    <h1 class="title">Projetos Pessoais</h1>

    <div v-for="project in projects" :key="project.id" class="card-projects">
      <img :src="project.image" alt="" />
      <div class="infos-container">
        <h1>{{ project.title }}</h1>
        <p>{{ project.description }}</p>
        <a
          class="link-space"
          :href="project.link"
          target="_blank"
          rel="noopener noreferrer"
          >Ver projeto</a
        >
        <a :href="project.repo" target="_blank" rel="noopener noreferrer"
          >Ver Repositório</a
        >
        <div class="techs-container">
          <span class="badge" v-for="tech in project.techs" :key="tech">{{
            tech
          }}</span>
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
          id: 3,
          image: require('@/assets/photos/crud-firebase.jpg'),
          title: 'Crud Vue e Firebase',
          link: 'https://crud-vue-firebase.netlify.app/',
          repo: 'https://github.com/joao-belmiro/frontend-test',
          description:
            'Crud simples de uma única entidade utilizando o firebase como banco dedados NOSQL, possui responsividade para dispositivos móveis, sendo hospedado na netlify',
          techs: ['Vue.js', 'javaScript', 'Git', 'HTML5', 'SASS']
        },
        {
          id: 2,
          image: require('@/assets/photos/fipe.jpg'),
          title: 'Seu Fipe',
          link: 'https://fipe-search.netlify.app/',
          repo: 'https://github.com/joao-belmiro/fipe-search',
          description:
            'Front-end desenvolvido com base em uma api aberta encontrada https://publicapis.dev/, nesta aplicação é feita a busca do valor de um veículo seja carro, motocicleta ou caminhão ,também é mostrado um gráfico com o histórico dos 3 últimos valores coletados, foi disponibilizado na netlify',
          techs: ['Nuxt.js', 'HTML5', 'CSS3', 'javaScript', 'Axios']
        },
        {
          image: require('@/assets/photos/letras.jpg'),
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
    display: block;
    border-left: 10px solid $primary ;
    padding-left: 16px;
  }
  h1 {
    font-size: 32px;
  }
  .card-projects {
    width: 80%;
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    border-radius: 4px;
    border: 1px solid $dark;
    box-shadow: 4px 4px 0px -1px rgba(0, 0, 0, 1);
    @media (max-width: 999px) {
      width: 100%;
      flex-direction: column;
    }
    img {
      margin: 16px;
      border-radius: 6px;
      width: 35%;
      height: 250px;
      @media (max-width: 999px) {
        border-radius: 4px 4px 0px 0px;
        margin: 0;
        height: 450px;
        width: 100%;
      }
      @media (max-width: 768px) {
        height: 300px;
      }
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
        line-height: 1.5em;
      }

      p {
        letter-spacing: 2px;
        margin-bottom: 10px;
        text-align: justify;
         @media (max-width: 999px) {
            letter-spacing: 1px;
            text-align: none;
         }
      }

      .link-space {
        margin-right: 16px;
      }
      a {
        text-decoration: none;
        color: $primary;
        font-size: 14px;
        text-transform: uppercase;
        letter-spacing: 2px;
        font-weight: 600;

        &:hover {
          opacity: 0.7;
        }
      }
    }
    .techs-container {
      margin-top: 16px;
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
