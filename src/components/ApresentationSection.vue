<template>
  <section id="apresentation" class="apresentation">
    <div class="profile-data">
      <img
        class="profile-image"
        src="@/assets/photos/my-photo.webp"
        alt="minha foto"
        width="320"
        height="320"
      />
      <div class="infos-profile">
        <a
          class="link github"
          target="_blank"
          href="https://github.com/joao-belmiro"
        >
          <img
            width="25"
            height="25"
            class="link-icon"
            src="@/assets/icons/github.svg"
            alt="logo github"
          />
          GitHub
        </a>
        <a
          class="link linkedin"
          target="_blank"
          href="https://www.linkedin.com/in/jo%C3%A3o-gon%C3%A7alves-40k/"
        >
          <img
            width="25"
            height="25"
            class="link-icon"
            src="@/assets/icons/linkedin-in-brands.svg"
            alt="logo linkedin"
          />
          Linkedin</a
        >
        <a
          class="curriculo"
          href="https://docs.google.com/uc?export=download&id=1w39Wl51AuYJuX1It3SCWlnTGAlrLEame"
          download
        >
          <img
            width="25"
            height="25"
            class="link-icon"
            src="@/assets/icons/download-solid.svg"
            alt="icone de download"
          />
          Baixar Currículo</a
        >
      </div>
    </div>
    <div class="apresentation-text">
      <h1>Olá, meu nome é João Carlos Belmiro Gonçalves</h1>
      <h2>Sou desenvolvedor de software</h2>
      <br />
      <p>
        Comecei não gostando de programação devido as más Experiencias na na faculdade
        , bem como a desmotivação devido a problemas como falta de dinheiro e perspectiva de futuro, devido as poucas oportunidades oferecidas pela instituição na época, no
        entanto com o desejo de sair da minha zona de conforto no final de <b>2019</b>,
        decidi estudar java, pois era uma linguagem que seria usada na
        faculdade, esses estudos <i>longos e chatos na época</i> me levaram da minha primeira vaga de estágio em
        programação até onde estou agora.
      </p>
    </div>
  </section>
</template>

<style lang="scss">
.apresentation {
  padding: 32px 0;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: flex-start;
  column-gap: 64px;
  color: $background;
  background: $dark;
  margin-bottom: 20px;
  border-radius: 0 0 80px 80px;
  @media (max-width: 900px) {
    flex-direction: column;
    row-gap: 32px;
    align-items: center;
    column-gap: 16px;
  }

  @media (max-width: 999px) {
    padding: 16px;
    border-radius: 0 0 30px 30px;
  }

  .profile-data {
    display: flex;
    flex-direction: column;
    row-gap: 64px;
    align-items: center;

    .infos-profile {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      column-gap: 4%;
      row-gap: 16px;

      .github {
        background: $primary;
      }
      .linkedin {
        background: $secondary;
      }

      .curriculo {
        width: 100%;
        background: $contrast;
      }

      a {
        line-height: 40px;
        text-align: center;
        display: block;
        color: #fff;
        height: 40px;
        text-decoration: none;
        font-size: 14px;
        font-weight: 600;
        letter-spacing: 2px;
        border-radius: 6px;
        &:hover {
          opacity: 0.7;
        }

        .link-icon {
          position: relative;
          top: 7px;
          margin-right: 10px;
          width: 25px;
        }
      }
      .link {
        display: block;
        width: 48%;
      }
    }
    .profile-image {
      border-radius: 50%;
      border: 8px solid $primary;
    }
  }
  .apresentation-text {
    width: 40%;
    @media (max-width: 999px) {
      width: 100%;
    }
    h1 {
      font-size: 32px;
      color: $primary;
      margin-bottom: 10px;
      letter-spacing: 1px;
    }

    h2 {
      margin-bottom: 16px;
      letter-spacing: 2px;
    }

    h3 {
      letter-spacing: 3px;
    }
    p {
      text-align: justify;
      letter-spacing: 1px;
      line-height: 2;
      @media (max-width: 999px) {
        line-height: 1.5;
      }
      @media (max-width: 768px) {
        line-height: 2;
      }
    }
  }
}
</style>
