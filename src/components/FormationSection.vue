<template>
  <section id="formation" class="formation">
    <div>
      <h1 class="title">Formação Acadêmica</h1>
      <div class="course-name">Engenharia da Computação</div>
      <h2>UFPA - Universidade Federal do Pará</h2>
      <p>fev de 2015 - ainda cursando</p>
      <br>
      <p>Curso com o foco em engenharia eletrica e telecomunicações, logo foram feitas muitas matérias de cálculo e propagação de ondas, possui os fundamentos de redes, lógica de programação, estruturas de dados em java, teoria da computação e inteligência artificial. Também fomenta a criatividade e o tralho em conjunto pois há matérias especificas para projetos de engenharia na área de eletrônica embarcada</p>
    </div>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss">
.formation {
  display: flex;
  flex-direction: row;
  justify-content: center;
  padding-bottom: 32px;
  @media (max-width: 999px) {
    margin: 0 16px;
  }
  div {
    width: 80%;
    @media (max-width: 999px) {
      width: 100%;
    }
    .title {
        border-left: 10px solid $primary ;
        padding-left: 16px;
        text-align: start;
        margin-bottom: 32px;
        font-size: 32px;
    }
    .course-name {
      font-size: 30px;
      font-weight: 650;
      letter-spacing: 3px;
      margin-bottom: 16px;
         @media (max-width: 999px) {
          font-size: 24px;
        }
    }
    h2 {
         @media (max-width: 999px) {
          font-size: 18px;
        }
    }
    p {
        letter-spacing: 2px;
        font-weight: 550;
        font-size: 18px;
           @media (max-width: 999px) {
            text-align: justify;
          font-size: 14px;
        }
    }
  }

}
</style>
