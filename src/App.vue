<template>
  <div id="app">
    <header>
      <nav>
        <div @click="clickMenu" class="mobile-menu">
          <div class="line1"></div>
          <div class="line2"></div>
          <div class="line3"></div>
        </div>
        <a class="logo" href="/"><span>/*</span> joão carlos <span>*/</span></a>
        <ul class="nav-list">
          <li><a href="#apresentation">Sobre</a></li>
          <li><a href="#jobs">Experiências</a></li>
          <li><a href="#projects">Projetos Pessoais</a></li>
          <li><a href="#formation">Formação</a></li>
        </ul>
      </nav>
    </header>
    <main>
      <Apresentation-section/>
      <Jobs-section/>
      <Personal-projects-section/>
      <Formation-section/>
    </main>
    <footer>
      <h4>
        © Todos os direitos reservados -
        <a
          href="https://github.com/joao-belmiro"
          target="_blank"
          rel="noopener noreferrer"
          >GitHub</a
        >
        João Carlos - 2022
      </h4>
    </footer>
  </div>
</template>
<script>
import ApresentationSection from './components/ApresentationSection.vue'
import JobsSection from './components/JobsSection.vue'
import PersonalProjectsSection from './components/PersonalProjectsSection.vue'
import FormationSection from './components/FormationSection.vue'
export default {
  components: {
    ApresentationSection,
    JobsSection,
    PersonalProjectsSection,
    FormationSection
  },
  data () {
    return {
      active: 'active'
    }
  },
  methods: {
    clickMenu () {
      const nav = document.querySelector('.nav-list')
      nav.classList.toggle(this.active)
    }
  }
}
</script>
<style lang="scss">
* {
  margin: 0;
  padding: 0;
}
body {
  @media (max-width: 999px) {
    overflow-x: hidden;
  }
}
#app {
  font-family: $global-font;
}
header {
  nav {
    display: flex;
    justify-content: space-around;
    align-items: center;
    min-height: 10vh;
    background-color: #000000;

    .logo {
      font-size: 22px;
      letter-spacing: 4px;
      text-transform: uppercase;
      text-decoration: none;
      color: $background;

      &:hover {
        opacity: 0.7;
      }

      @media (max-width: 999px) {
        font-size: normal;
        padding-right: 16px;
      }
      span {
        color: $primary;
      }
    }

    .mobile-menu {
      display: none;
      cursor: pointer;

      @media (max-width: 999px) {
        display: block;

        &:hover {
          opacity: 0.7;
        }
      }

      div {
        width: 32px;
        height: 2px;
        background: $background;
        margin: 8px;
      }
    }

    .nav-list {
      display: flex;
      list-style: none;

      @media (max-width: 900px) {
        padding: 50px 0;
        position: absolute;
        top: 10vh;
        left: 0;
        width: 100%;
        height: 85vh;
        background: #000000;
        flex-direction: column;
        row-gap: 100px;
        align-items: center;
        transform: translateX(-100%);
        transition: 0.5s ease-in;
        z-index: 2;
      }
      li {
        letter-spacing: 3px;
        margin-left: 32px;
        @media (max-width: 999px) {
          margin-left: 12px;
        }

        a {
          position: relative;
          text-decoration: none;
          color: $background;
          display: inline-block;
          padding-top: 10px;
          padding-bottom: 5px;
          overflow-x: hidden;
          &:hover {
            color: $background;
          }
          &:before {
            content: "";
            position: absolute;
            bottom: 0;
            transition: transform 0.5s ease;
            height: 2px;
            background: $background;
            transform: translateX(-100%);
          }
          &:hover:before {
            width: 100%;
            transform: translateX(0);
          }
        }
      }
    }
    .active {
      transform: translateX(0);
    }
  }
}
main {
  min-height: 80vh;
  background-color: $background;
}
footer {
  background-color: #000000;
  text-align: center;
  color: $background;

  h4 {

    @media (max-width: 999px) {
      font-size: 11px;
    }

    line-height: 10vh;

    a {
      text-decoration: none;
      color: $accent;
      &hover {
        opacity: 0.7;
      }
    }
  }
}
</style>
