# Projeto 5 - 1º semestre de 2023

### Parceiro Acadêmico

MidAll [B] 

![MidAll](https://user-images.githubusercontent.com/79945984/225166828-fd8d6942-68e5-4c26-9466-06bc7b08e0d0.png)

### *MidAllº [B]*

### Visão do Projeto

<p align="justify">
Esse projeto visa automatizar a jornada de controle de seus arquivos armazenados em uma plataforma de vídeos, transferindo-os para a nuvem, por meio do desenvolvimento de um aplicativo como serviço, com apenas um menu de configuração para o usuário, que terá os parâmetros necessários para o processo de serviço de download de forma automática, gerando alertas em caso de erro no processamento. Fica responsável por salvar os metadados do arquivo para construir um painel de controle para monitorar a execução do serviço e posteriormente analisar resultados e indicadores.
</p>

Link do repositório do projeto: https://github.com/TechNinjass/midall-parent

## Tecnologias utilizadas

### Vue [![Vue.js](https://img.shields.io/badge/Vue.js-%234FC08D.svg?style=for-the-badge&logo=vue.js&logoColor=white)](https://vuejs.org/)

Vue.js é um framework JavaScript de código aberto para a criação de interfaces de usuário reativas e eficientes. Com uma sintaxe intuitiva e uma curva de aprendizado suave, o Vue.js facilita a construção de interfaces modulares e reutilizáveis.

Clique [aqui](https://vuejs.org/), para acessar a documentação oficial.

### Tailwind css  [![Tailwind CSS](https://img.shields.io/badge/Built_with-Tailwind_CSS-38B2AC?logo=tailwind-css&style=flat-square)](https://tailwindcss.com/)

O Tailwind CSS é um framework de CSS que usa classes utilitárias para estilizar diretamente o HTML, agilizando o desenvolvimento front-end. Ele oferece uma ampla gama de classes pré-definidas para estilos, margens, cores e responsividade, permitindo criar interfaces atraentes de forma rápida e flexível.

Clique [aqui](https://element-plus.org/), para acessar a documentação oficial.

### Flask [![Flask](https://img.shields.io/badge/Flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white)](http://flask.pocoo.org/)


O Flask é um framework leve em Python para construção de aplicativos web. Ele oferece ferramentas para criar rapidamente aplicações web simples a complexas, seguindo o padrão de arquitetura MVC (Model-View-Controller). 

Clique [aqui](https://flask.palletsprojects.com/en/2.3.x/), para acessar a documentação oficial.


### SQL-Alchemy [![SQL-Alchemy](https://img.shields.io/badge/SQL--Alchemy-%230D6A8F.svg?style=for-the-badge&logo=sqlalchemy&logoColor=white)](https://www.sqlalchemy.org/)

O SQL-Alchemy é uma biblioteca em Python que fornece uma abstração flexível para trabalhar com bancos de dados relacionais. Ele permite que os desenvolvedores criem consultas SQL de maneira programática, mapeiem objetos Python para tabelas do banco de dados e gerenciem interações complexas com o banco de dados de forma eficiente.

Clique [aqui](https://docs.sqlalchemy.org/), para acessar a documentação oficial.


## Contribuições pessoais

Nesta empreitada, assumi a responsabilidade pela concepção e desenvolvimento da interface gráfica. Empreguei o Vue.js 3 como um dos pontos principais da aplicação. A configuração das rotas foi realizada utilizando vue-router, e a estlização de componentes mais dinâmicos e personalizados do projeto foi estruturada utilizando o Tailwind CSS. Também foi definido para mim a tarefa da criação das estruturas de dados em Python mais conhecidas como models, e para realizar está tarefa utilizei à biblioteca SQL-Alchemy.

Para o gerenciamento, fluxo e armazenameto de dados, optamos pela sinergia entre as plataformas Google Cloud e Azure pela disponibilidade com a conta de estudante fornecido pela instituição acadêmica. Aproveitando as APIs nativas do Google, habilitamos a transferência fluida de dados entre estas nuvens.

Este projeto configurou-se como uma notável oportunidade para aprimorar minhas competências como um desenvolvedor e cultivar uma experiência prática embasada em tecnologias que cada vez mais vem se mostrando mais requisitadas. Nesse âmbito, pude expandir meu entendimento e aplicação das ferramentas essenciais, reforçando minha capacidade de oferecer soluções inovadoras em possiveis novos futuros projetos desafiadores.

<details><summary>Tela Login</summary>

> Uma breve visualização da tela de Login que foi feito através do framework Vuejs com elementos da biblioteca Element Plus que é exclusiva do framework

```kotlin
<template>
  <div id="page">
    <div id="loginBackgorund">
      <div>
        <img src="../assets/Logo.svg">
        <p style="margin-top: auto;">da Subiter.</p>
      </div>
      <div>
        <p>Bem-vindo</p>
        <p>De volta!</p>
      </div>
      <div>
        <p>Alcance o invisível, Subiter</p>
      </div>
    </div>
    <div id="loginMain">
      <div id="loginContent">
        <section id="welcome">
          <h1>Login</h1>
          <div>
            <img src="../assets/Icons/Info.svg" style="width: 12px; margin:1px 7px;"/>
            <span>
              <p>Olá, amigo! Por favor entre no</p>
              <p>Sistema de Gerenciamento de Controle.</p>
            </span>
          </div>
        </section>
        <LoginForm/>
      </div>
    </div>
  </div>
</template>
 
<script> 
import LoginForm from '../components/form/LoginForm.vue'
export default {
  name:"Login",
  components:{
    LoginForm
  }
}
</script> 
```
</details>

Também fiquei responsável pela parte dos gráficos, utilizando a api do Google o google charts

<details><summary>Gráficos</summary>

> Aqui, um trecho da tela Home com foco no desenvolvimento dos gráficos, foram feitos utilizando uma Api do próprio Google, o GoogleCharts, para sincronizar com os dados refrentes ao usuário Cliente logado no sistema.

```kotlin
<template> 
  <link href='https://fonts.googleapis.com/css?family=Inter' rel='stylesheet'/> 
  <BasePage>
    <Title title="Dashboard"/>
    <div class="cards">
      <el-card class="card"> 
        <section id="top-card">
          <div>
            <h1>Olá!</h1>
            <p>Este é o seu Dashboard, aqui você tem acesso aos principais indicadores de
            desempenho que são relevantes para o seu dia a dia no MCS.</p>
          </div>
          <img src="../assets/Home_Img.svg" style="width: 300px;"/>
        </section>
      </el-card>
      <div id="charts">
        <el-card class="card">
          <h3>Quantidade de chamados</h3>
          <GChart
            type="PieChart"
            :data="this.chamadosChart.data"
            :options="this.chamadosChart.options"
            v-if="this.chamadosChart.total>0"
          />
          <p>Total de {{this.chamadosChart.total}} chamados</p>
        </el-card>
        <el-card class="card">
          <h3>Linha do tempo</h3>
          <el-select v-model="this.monthChart.year" placeholder="Select">
            <el-option
              v-for="(item,index) in this.monthChart.data"
              :key="index"
              :label="index"
              :value="index"
            />
          </el-select>
          <GChart
            type="LineChart"
            :data="this.monthChart.data[this.monthChart.year]"
          />
        </el-card>
      </div>
  </div>
  </BasePage>
</template>
<script>
  import BasePage from '../components/layout/BasePage.vue'
  import Title from '../components/content/Title.vue'
  import {ElCard} from 'element-plus'
  import CardList from '../components/content/CardList.vue'
  import {GChart} from 'vue-google-charts'
  export default{
    name:"Dashboard",
    components:{
      BasePage,
      Title,
      ElCard,
      CardList,
      GChart
    },
    data(){
      return{
        chamadosChart:{
          data:null,
          options:{
            slices: {
              0: { color: '#F56C6C' },
              1: { color: '#E6A23C' },
              2: { color: '#67C23A' }
            }
          },
          total:0
        },
        monthChart:{
          data:{},
          year:null
        }
      }
    },
    async created(){
      await this.$store.dispatch("listChamados")
      this.chamadosChart.data = this.$store.getters.getChamadoChartData
      this.monthChart.data = this.$store.getters.getMonthChartData
      this.monthChart.year = new Date().getFullYear()
      console.log(this.monthChart.data)
      this.chamadosChart.total = (this.chamadosChart.data[1][1]+this.chamadosChart.data[2][1]+this.chamadosChart.data[3][1]) 
    }
  };
</script>
```
</details>

## Aprendizados Efetivos ![Aprendizados efetivos](https://img.shields.io/badge/Aprendizados%20efetivos-100%25-brightgreen?style=for-the-badge)
Este projeto representou uma oportunidade de aprendizado significativa, durante a qual fui introduzido ao conceito de DevOps, um ecossistema substancialmente diferente da minha familiaridade prévia. Este novo domínio me permitiu explorar a computação em nuvem, engajando-me na transferência eficiente de arquivos entre serviços em nuvem distintos. Adotando a metodologia GitFlow, assumi a responsabilidade de incorporá-la ao projeto, aplicando seus princípios de forma a estabelecer nossa própria abordagem personalizada.

A experiência acumulada ao longo deste projeto foi profundamente enriquecedora. Tive a oportunidade de aplicar conceitos teóricos em um contexto prático, enfrentando desafios intrincados que ampliaram meu entendimento do desenvolvimento de aplicações web. Esta vivência consolida minha proficiência nas tecnologias empregadas, enquanto expande meu repertório de habilidades. Dessa forma, estou mais bem preparado para enfrentar com confiança projetos desafiadores no futuro.

- Aplicar conceitos de DevOps, como o GitFlow: Sei fazer com autonomia.
- Criação das models com o SQL-Alchemy: Sei fazer com autonomia.
- Desenvolvimento da interface principal em Vue js 3: Sei fazer com autonomia. 

## Navegação Entre Projetos :link:
 
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Julius.md"> 1º Semestre: Julius - Assistente virtual criado para facilitar a sua vida financeira</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/SGBD_Health.md"> 2º Semestre: SGBD Health - Aplicação de monitoramento com foco em performance e desempenho</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Descont0n.md"> 3° Semestre: Descont0n - Ferramenta para criação de promoções e regras de negócio com foco em E-commerce</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/MCS.md"> 4° Semestre: MCS - Sistema ERP que visa gerenciar e controlar dados fornecidos pelos clientes</a></li></p>
<p align="justify" style="font-family:roboto;"><li> 5° Semestre: TECH NINJAS - Sistema de automatização para fluxo de controle dos arquivos armazenados em cloud
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/README.md"> Voltar para página inicial</a></li></p>
