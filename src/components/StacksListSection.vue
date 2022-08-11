<template>
  <section id="stacks" class="stacks-section">
    <div class="container">
      <h1>Tecnolgias Estudadas</h1>
      <div class="line-scroll">
        <button @click="scrollBy(-300,0)" class="prev-btn">&#10094;</button>
        <div class="cover">
          <div class="list-stacks">
            <div v-for="stack in stacks" :key="stack.alt" class="tech-card">
              <img :src="stack.img" :alt="stack.alt" />
            </div>
          </div>
        </div>
        <button @click="scrollBy(300,0)" class="next-btn">&#10095; </button>
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
          alt: 'nuxt stack'
        },
        {
          img: require('@/assets/stacks/vue.svg'),
          alt: 'vue stack'
        },
        {
          img: require('@/assets/stacks/javaScript.svg'),
          alt: 'javaScript stack'
        },
        {
          img: require('@/assets/stacks/css.svg'),
          alt: 'css stack'
        },
        {
          img: require('@/assets/stacks/html5.svg'),
          alt: 'html5 stack'
        },
        {
          img: require('@/assets/stacks/git.svg'),
          alt: 'git stack'
        },
        {
          img: require('@/assets/stacks/gitlab.svg'),
          alt: 'gitlab stack'
        },
        {
          img: require('@/assets/stacks/github.svg'),
          alt: 'github stack'
        },
        {
          img: require('@/assets/stacks/sass.svg'),
          alt: 'sass stack'
        },
        {
          img: require('@/assets/stacks/eslint.svg'),
          alt: 'eslint stack'
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
        font-weight: 600;
        display: block;
        background-color: $background;
        width: 50px;
        height: 50px;
        color: $primary;
        text-align: center;
        color: $primary;
         @media (max-width: 999px) {
          width: 30px;
          height: 30px;
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
        width: 75%;
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
            padding: 32px;
            border-radius: 9px;
            border: 2px solid $dark;
            display: flex;
            align-items: center;
            height: 130px;
            transition: transform 1s;

            &:hover {
              transform: scale(1.2);
              cursor: pointer;
              border: 2px solid $primary;
            }
          }
        }
      }
    }
  }
}
</style>
