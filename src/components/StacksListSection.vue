<template>
  <section id="stacks" class="stacks-section">
    <div class="container">
      <h1>Tecnolgias Estudadas</h1>
      <div class="line-scroll">
        <button @click="scrollBy(-200,0)" class="prev-btn">&#10094;</button>
        <div class="cover">
          <div class="list-stacks">
            <div v-for="stack in stacks" :key="stack.alt" class="tech-card">
              <p>{{stack.name}}</p>
              <img :src="stack.img" :alt="stack.alt" />
            </div>
          </div>
        </div>
        <button @click="scrollBy(200,0)" class="next-btn">&#10095;</button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data () {
    return {
      stacks: [
        {
          img: require('@/assets/stacks/nuxt.svg'),
          alt: 'nuxt stack',
          name: 'Nuxt.js'
        },
        {
          img: require('@/assets/stacks/vue.svg'),
          alt: 'vue stack',
          name: 'Vue.js'
        },
        {
          img: require('@/assets/stacks/javaScript.svg'),
          alt: 'javaScript stack',
          name: 'javaScript'
        },
        {
          img: require('@/assets/stacks/css.svg'),
          alt: 'css stack',
          name: 'CSS3'
        },
        {
          img: require('@/assets/stacks/sass.svg'),
          alt: 'sass stack',
          name: 'SASS'
        },
        {
          img: require('@/assets/stacks/html5.svg'),
          alt: 'html5 stack',
          name: 'HTML5'
        },
        {
          img: require('@/assets/stacks/git.svg'),
          alt: 'git stack',
          name: 'Git'
        },
        {
          img: require('@/assets/stacks/gitlab.svg'),
          alt: 'gitlab stack',
          name: 'GitLab'
        },
        {
          img: require('@/assets/stacks/github.svg'),
          alt: 'github stack',
          name: 'GitHub'
        },
        {
          img: require('@/assets/stacks/eslint.svg'),
          alt: 'eslint stack',
          name: 'ESLint'
        }
      ]
    }
  },
  methods: {
    scrollBy (horizontal, vertical) {
      const listScroll = document.querySelector('.list-stacks')
      listScroll.scrollBy(horizontal, vertical)
    }
  }
}
</script>

<style lang="scss">
.stacks-section {
  display: flex;
  flex-direction: row;
  justify-content: center;
  margin:0 16px 32px 15px;
  .container {
    width: 80%;
      @media (max-width: 999px) {
          width: 100%;
        }
    h1 {
      box-sizing: border-box;
      border-left: 10px solid $primary;
      padding-left: 16px;
      text-align: start;
      margin-bottom: 32px;
      font-size: 32px;
    }
    .line-scroll {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      button {
        cursor: pointer;
        border: none;
        border-radius: 50%;
        font-size: 25px;
        font-weight: 700;
        display: block;
        background-color: $background;
        width: 50px;
        height: 50px;
        color: $primary;
        text-align: center;
        color: $primary;
        display: flex;
        justify-content: center;
        align-items: center;
         @media (max-width: 999px) {
          width: 40px;
          height: 40px;
          font-size: 20px;
        }
      }
      .prev-btn {
        &:hover {
          background-color: #E8E8E8;
        }
      }
      .next-btn {
        text-align: center;
        &:hover {
          background-color: #E8E8E8;
        }
      }
      .cover {
        position: relative;
        width: 88%;
        .list-stacks {
          scroll-behavior: smooth;
          width: 100%;
          display: flex;
          flex-direction: row;
          column-gap: 48px;
          align-items: center;
          overflow: hidden;
          height: 250px;
          position: relative;
          .tech-card {
            position: relative;
            display: flex;
            flex-direction: column;
            padding: 0px 32px 32px 32px;
            border-radius: 9px;
            border: 2px solid $dark;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 150px;
            transition: transform 1s;

            &:first-child {
              margin-left: 16px;
            }
            &:last-child {
              margin-right: 16px;
            }
            &:hover {
              transform: scale(1.2);
              cursor: pointer;
              border: 2px solid $primary;
            }
            p {
              padding: 16px 0 10px 0;
              display: block;
              position: relative;
              line-height: 32px;
              font-weight: 600;
              opacity: 0;
            }

            &:hover p {
              opacity: 1;
              transition: opacity 1s;
            }
            img {
              position: relative;
            }
          }
        }
      }
    }
  }
}
</style>
