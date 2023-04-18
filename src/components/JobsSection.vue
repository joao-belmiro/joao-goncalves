<template>
  <section id="jobs" class="jobs-section">
    <h1>Experiência profissional</h1>
    <details :open="index === 0 ? true: false" v-for="(job, index) in jobs" :key="job.id">
        <summary>{{job.company}}</summary>
        <div class="detail-content">
            <p><strong>{{job.rangeTime}} {{ diffMonths(job.initDate, job.endDate) }}</strong></p>
            <br>
            <p>{{job.type}} - <i>{{job.regim}}</i></p>
            <br>
            <p class="description">{{job.description}}</p>
            <br>
            <div class="techs-list">
             <span v-for="tech in job.techs" :key="tech">
                {{tech}}
             </span>
            </div>
        </div>
    </details>
  </section>
</template>

<script>
export default {
  data () {
    return {
      jobs: [
        {
          id: 3,
          company: 'Compass.uol',
          regim: 'Clt',
          type: 'Desenvolvedor Front-end Pleno',
          initDate: new Date('2021-08-09'),
          endDate: new Date(Date.now()),
          rangeTime: 'ago de 2021 - ainda atuando - ',
          description: 'Atuando como Front-end, fui alocado na vivo telefonica sendo responsável por desenvolver novas features para o simulador do e-commerce B2B da vivo, também era responsável pela correção de bugs, testes End to End, desenvolvimento de componentes reutilizáveis, decompor e estimar histórias vindas do backlog da sprint.',
          techs: [
            'Vue.js',
            'javaScript',
            'Git (Gitlab)',
            'AEM (Adobe Experience Manager)',
            'HTML5',
            'SASS',
            'Java 8 , 11',
            'Api Rest',
            'Scrum'
          ]
        },
        {
          id: 4,
          company: 'Operand',
          regim: 'PJ',
          type: 'Desenvolvedor Front-end Pleno',
          initDate: new Date('2022-08-01'),
          endDate: new Date('2023-01-01'),
          rangeTime: 'ago de 2022 jan de 2023 - ',
          description: 'Responsável por dar manutenção e impementar pequenas features no sistema legado de degetão de agências de publicidade, utlizando JavaScript, HTML5, SCSS',
          techs: [
            'Vue.js',
            'javaScript',
            'JQuery',
            'Git (Gitlab)',
            'HTML5',
            'SCSS',
            'Api Rest'
          ]
        },
        {
          id: 2,
          company: 'PD Case informática Ltda.',
          regim: 'Clt',
          type: 'Desenvolvedor Full-stack',
          initDate: new Date('2020-10-15'),
          endDate: new Date('2021-08-19'),
          rangeTime: 'out de 2020 - ago de 2021 - ',
          description: 'Desenvolvedor reponsável por criar novas aplicações com base nos padrões do Banco da Amazônia, utilizando a arquitetura de microsserviços desde o back-end até o front-end, atuei principalmente em dois sistemas. O primeiro foi Um sistema de renegociação de contratos, era um CRM que servia para gerar propostas de pagamentos de contratos de um determinado cliente do banco. Paralelo a esse sistema atuei em mais um CRM para a gestão de indicadores do banco ',
          techs: [
            'Vue.js',
            'Quasar framework',
            'HTML5',
            'CSS3',
            'javaScript',
            'Git (Gitlab)',
            'Java 8',
            'Spring framework',
            'Api Rest',
            'Oracle Db'
          ]
        },
        {
          id: 1,
          company: 'Banco da Amazônia SA.',
          regim: 'Contrato',
          type: 'Estágio',
          initDate: new Date('2019-05-02'),
          endDate: new Date('2020-08-01'),
          rangeTime: 'mai de 2019 - out de 2020 - ',
          description: 'Encarregado de adquirir conhecimento para exercer as atividades da empresa, sob orientação dos desenvolvedores do banco, atuei na correção de bugs, criação de novos cruds, mapeamentos de entidades no banco de dados e reuniões com coordenadorias clientes',
          techs: [
            'Java 8',
            'Spring boot',
            'Oracle Db',
            'javaScript',
            'jQuery',
            'Git (Gitlab)',
            'Knockout.JS',
            'HTML5',
            'CSS3',
            'Vue.js'
          ]
        }
      ]
    }
  },
  methods: {
    diffMonths (initDate, endDate) {
      const diference = (endDate.getTime() - initDate.getTime()) / (1000 * 60 * 60 * 24 * 30.44)
      const diffMonths = (Math.round(diference))
      const intMonths = Math.floor(diffMonths / 12)
      return diffMonths > 12 ? `${intMonths} ano${intMonths > 1 ? 's' : ''} e ${diffMonths % 12} meses` : `${diffMonths} meses`
    }
  }
}
</script>

<style lang="scss">
.jobs-section {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;

    @media (max-width: 999px) {
        margin: 0 16px;
        align-items: flex-start;
    }
    h1 {
        width: 80%;
        box-sizing: border-box;
        text-align: start;
        border-left: 10px solid $primary ;
        padding-left: 16px;
        margin-bottom: 32px;
        font-size: 32px;
        @media (max-width: 999px) {
          font-size: 21px;
        }
    }

    details {
      summary {
        font-weight: 600;
        position: relative;
        cursor: pointer;
        border: 1px solid #000;
        padding: 12px 0;
        border-radius: 6px;
        list-style: none;

        &:before {
          font-size: 20px;
          content: '\2193';
          color: $dark;
          padding: 0 16px;
          font-weight: 700;
        }
      }

        &[open] summary:before {
            content: '\2191';
        }

        &[open] summary {
            border-radius: 6px 6px 0 0;
        }

        &[open] .detail-content {
            border-radius: 0px 0px 6px 6px;
        }

        .detail-content {
            border-left: 1px solid #000;
            border-right: 1px solid #000;
            border-bottom: 1px solid #000;
            padding: 24px 16px;

            .description {
                text-align: justify;
                letter-spacing: 2px;
                @media (max-width: 999px) {
                  font-size: 12px;
                  letter-spacing: 1px;
                }
            }

            .techs-list {
                display: flex;
                flex-direction: row;
                flex-wrap: wrap;
                row-gap: 12px;
                column-gap: 12px;

                span {
                    font-size: 10px;
                    font-weight: 550;
                    letter-spacing: 1px;
                    line-height: 24px;
                    border-radius: 15px;
                    padding: 0 12px;
                    background: $primary;
                    color:#fff;
                }
            }
        }
        width: 80%;
        margin-bottom: 32px;
        box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1), 0px 8px 16px rgba(0, 0, 0, 0.1);
        @media (max-width: 999px) {
            width: 100%;
        }
    }
}
</style>
