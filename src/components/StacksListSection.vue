<template>
  <section id="stacks" class="stacks-section">
    <div class="container">
      <h1>Tecnolgias Trabalhadas</h1>
      <a
        href="https://www.figma.com/file/b6eE2L4Uqrg7fT5XfyHfKi/Tech-Stack-Icons-%26-Design-Stack-Icons-(Community)?node-id=19-1174&t=4R3ygYYxjPEzrfqe-0"
        target="_blank"
        rel="noopener noreferrer"
      >
        <strong>Referência dos Ícones </strong></a
      >
      <div class="line-scroll">
        <div class="cover">
          <div @mouseenter="enterList" class="list-stacks">
            <div
              @click="isDown = false"
              v-for="stack in stacks"
              :key="stack.alt"
              class="tech-card"
            >
              <p>{{ stack.name }}</p>
              <img :src="stack.img" :alt="stack.alt" width="100" height="90" />
            </div>
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
          img: require('@/assets/stacks/adobe.svg'),
          alt: 'adobe',
          name: 'Adobe experience Manager '
        },
        {
          img: require('@/assets/stacks/javaScript.svg'),
          alt: 'javaScript stack',
          name: 'javaScript'
        },
        {
          img: require('@/assets/stacks/quasar.svg'),
          alt: 'quasar framework',
          name: 'Quasar Framework'
        },
        {
          img: require('@/assets/stacks/sass.svg'),
          alt: 'sass stack',
          name: 'SASS'
        },
        {
          img: require('@/assets/stacks/java.svg'),
          alt: 'java stack',
          name: 'Java 11'
        },
        {
          img: require('@/assets/stacks/spring.svg'),
          alt: 'spring stack',
          name: 'spring boot'
        },
        {
          img: require('@/assets/stacks/bootstrap5.svg'),
          alt: 'bootstrap5 stack',
          name: 'Bootstrap 5'
        },
        {
          img: require('@/assets/stacks/vuetify.svg'),
          alt: 'vuetify',
          name: 'vuetify'
        },
        {
          img: require('@/assets/stacks/firebase.svg'),
          alt: 'firebase stack',
          name: 'firebase'
        },
        {
          img: require('@/assets/stacks/css.svg'),
          alt: 'css stack',
          name: 'CSS3'
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
      ],
      startX: 0,
      isDown: false,
      scrollLeft: 0
    }
  },
  methods: {
    isMobile () {
      let check = false;
      // eslint-disable-next-line no-useless-escape
      (function (a) { if (/(android|bb\d+|meego).+mobile|avantgo|bada\/|blackberry|blazer|compal|elaine|fennec|hiptop|iemobile|ip(hone|od)|iris|kindle|lge |maemo|midp|mmp|mobile.+firefox|netfront|opera m(ob|in)i|palm( os)?|phone|p(ixi|re)\/|plucker|pocket|psp|series(4|6)0|symbian|treo|up\.(browser|link)|vodafone|wap|windows ce|xda|xiino/i.test(a) || /1207|6310|6590|3gso|4thp|50[1-6]i|770s|802s|a wa|abac|ac(er|oo|s\-)|ai(ko|rn)|al(av|ca|co)|amoi|an(ex|ny|yw)|aptu|ar(ch|go)|as(te|us)|attw|au(di|-m|r |s )|avan|be(ck|ll|nq)|bi(lb|rd)|bl(ac|az)|br(e|v)w|bumb|bw\-(n|u)|c55\/|capi|ccwa|cdm\-|cell|chtm|cldc|cmd\-|co(mp|nd)|craw|da(it|ll|ng)|dbte|dc\-s|devi|dica|dmob|do(c|p)o|ds(12|\-d)|el(49|ai)|em(l2|ul)|er(ic|k0)|esl8|ez([4-7]0|os|wa|ze)|fetc|fly(\-|_)|g1 u|g560|gene|gf\-5|g\-mo|go(\.w|od)|gr(ad|un)|haie|hcit|hd\-(m|p|t)|hei\-|hi(pt|ta)|hp( i|ip)|hs\ -c|ht(c(\-| |_|a|g|p|s|t)|tp)|hu(aw|tc)|i\-(20|go|ma)|i230|iac( |\-|\/)|ibro|idea|ig01|ikom|im1k|inno|ipaq|iris|ja(t|v)a|jbro|jemu|jigs|kddi|keji|kgt( |\/)|klon|kpt |kwc\-|kyo(c|k)|le(no|xi)|lg( g|\/(k|l|u)|50|54|\-[a-w])|libw|lynx|m1\-w|m3ga|m50\/|ma(te|ui|xo)|mc(01|21|ca)|m\-cr|me(rc|ri)|mi(o8|oa|ts)|mmef|mo(01|02|bi|de|do|t(\-| |o|v)|zz)|mt(50|p1|v )|mwbp|mywa|n10[0-2]|n20[2-3]|n30(0|2)|n50(0|2|5)|n7(0(0|1)|10)|ne((c|m)\-|on|tf|wf|wg|wt)|nok(6|i)|nzph|o2im|op(ti|wv)|oran|owg1|p800|pan(a|d|t)|pdxg|pg(13|\-([1-8]|c))|phil|pire|pl(ay|uc)|pn\-2|po(ck|rt|se)|prox|psio|pt\-g|qa\-a|qc(07|12|21|32|60|\-[2-7]|i\-)|qtek|r380|r600|raks|rim9|ro(ve|zo)|s55\/|sa(ge|ma|mm|ms|ny|va)|sc(01|h\-|oo|p\-)|sdk\/|se(c(\-|0|1)|47|mc|nd|ri)|sgh\-|shar|sie(\-|m)|sk\-0|sl(45|id)|sm(al|ar|b3|it|t5)|so(ft|ny)|sp(01|h\-|v\-|v )|sy(01|mb)|t2(18|50)|t6(00|10|18)|ta(gt|lk)|tcl\-|tdg\-|tel(i|m)|tim\-|t\-mo|to(pl|sh)|ts(70|m\-|m3|m5)|tx\-9|up(\.b|g1|si)|utst|v400|v750|veri|vi(rg|te)|vk(40|5[0-3]|\-v)|vm40|voda|vulc|vx(52|53|60|61|70|80|81|83|85|98)|w3c(\-| )|webc|whit|wi(g |nc|nw)|wmlb|wonu|x700|yas\-|your|zeto|zte\-/i.test(a.substr(0, 4))) { check = true } })(navigator.userAgent || navigator.vendor || window.opera)
      return check
    },
    enterList () {
      const slider = this.$el.querySelector('.list-stacks')
      if (!this.isMobile()) {
        this.scrollDeskTop(slider)
      } else {
        this.scrollMobile(slider)
      }
    },
    scrollDeskTop (slider) {
      slider.addEventListener('mousedown', (e) => {
        this.isDown = true
        this.startX = e.pageX - slider.offsetLeft
        this.scrollLeft = slider.scrollLeft
      })

      slider.addEventListener('mouseleave', () => {
        this.isDown = false
      })

      slider.addEventListener('mouseup', () => {
        this.isDown = false
      })

      slider.addEventListener('mousemove', (e) => {
        if (!this.isDown) return
        e.preventDefault()
        const x = e.pageX - slider.offsetLeft
        const walk = x - this.startX
        slider.scrollLeft = this.scrollLeft - walk
      })
    },
    scrollMobile (slider) {
      slider.addEventListener('touchstart', (e) => {
        this.isDown = true
        this.startX = e.touches[0].pageX
      })
      slider.addEventListener('touchmove', (e) => {
        if (!this.isDown) return
        e.preventDefault()
        const multiplier = this.isMobile ? 0.9 : 2
        const x = e.touches[0].pageX
        const walk = (x - this.startX) * multiplier
        slider.scrollLeft += -walk
      })
    }
  }
}
</script>

<style lang="scss">
.stacks-section {
  display: flex;
  flex-direction: row;
  justify-content: center;
  margin: 0 16px 32px 15px;

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
      @media (max-width: 999px) {
        font-size: 22px;
      }
    }

    a {
      margin-left: 16px;
      text-decoration: none;
      color: $primary;
      font-size: 20px;
      letter-spacing: 1px;
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
          background-color: #e8e8e8;
        }
      }

      .next-btn {
        text-align: center;

        &:hover {
          background-color: #e8e8e8;
        }
      }

      .cover {
        position: relative;
        width: 100%;

        .list-stacks {
          width: 100%;
          display: flex;
          flex-direction: row;
          column-gap: 38px;
          align-items: center;
          overflow: hidden;
          height: 250px;
          position: relative;
          @media (max-width: 999px) {
            scroll-behavior: smooth;
            -webkit-overflow-scrolling: touch;
          }
          .tech-card {
            object-fit: contain;
            position: relative;
            display: flex;
            flex-direction: column;
            padding: 0px 32px 32px 32px;
            border-radius: 9px;
            border: 1px solid $grey-2;
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
              transform: scale(1.1);
              cursor: pointer;
              border: 1px solid $primary;
            }

            p {
              padding: 16px 0 10px 0;
              display: block;
              text-align: center;
              position: relative;
              font-weight: 500;
              opacity: 0;
              line-height: 1.1rem;
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
