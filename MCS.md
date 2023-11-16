# Projeto 4: 2º Semestre de 2022

### Parceiro Acadêmico

Subiter

<img src="https://user-images.githubusercontent.com/79945984/234428920-7718492b-5552-4f0a-88bc-8fbfdce87773.png" height="300"/>

### *Subiter*

### Visão do Projeto

<p style="text-align: justify;">
Sistema ERP que visa gerenciar e controlar dados, afim de reduzir custos, facilitar tomadas de decisão, otimizar o tempo de atendimento de chamados e aprimorar o solucionamento destes. É composta por níveis de usuários, onde o administrador terá controle sobre todas as funcionalidades existentes, dentre elas o cadastro, edição e exclusão de outros usuários; o suporte ficará responsável pelo CRUD de falhas e soluções genéricas e CRUD de equipamentos; o cliente trará o problema para o suporte e, este ficará responsável por gerenciar o chamado e resolvê-los.

A MCS (Management and Control System) trouxe de uma forma fácil e rápida o mais importante: o mapeamento gráfico de anomalias nas silhuetas. O Mapemamento de anomalias consiste pode ser utilizada durante, ou após uma inspeção, o suporte conseguirá fazer o upload da silhueta e adicionar as falhas (específicas daquele chamado) encontradas em formas e tamanhos diferentes para uma melhor identificação da posição e tamanho, facilitando na identificação de quantidade e quais materiais serão utilizados para a solução dessas falhas e também no cálculo do orçamento.
</p>

Para acessar o vídeo de demonstração da aplicação em uso, clique [aqui](https://www.youtube.com/watch?v=omSyXxA3AYI&list=PLUOBqJKbljZv85QQ4B3ExV93PQVVf8n2o)

[<img src="https://github.com/DolphinDatabase/MCS/blob/main/Imagens/MCS_Youtube.png" width="40%">](https://www.youtube.com/watch?v=omSyXxA3AYI&list=PLUOBqJKbljZv85QQ4B3ExV93PQVVf8n2o "MCS vídeo Demonstração")

### *Demonstração MCS*

Link do repositório do projeto: https://github.com/DolphinDatabase/MCS

## Tecnologias Utilizadas 💻

### Vue [![Vue.js](https://img.shields.io/badge/Vue.js-%234FC08D.svg?style=for-the-badge&logo=vue.js&logoColor=white)](https://vuejs.org/)
<p style="text-align: justify;">
Vue.js é um framework JavaScript de código aberto para a criação de interfaces de usuário reativas e eficientes. Com uma sintaxe intuitiva e uma curva de aprendizado suave, o Vue.js facilita a construção de interfaces modulares e reutilizáveis.

Clique [aqui](https://vuejs.org/), para acessar a documentação oficial.
</p>

### Element Plus [![Element Plus](https://img.shields.io/badge/Element_Plus-%231eaf7a.svg?style=for-the-badge&logo=vue.js&logoColor=white)](https://element-plus.org/)

<p style="text-align: justify;">
O Element Plus é uma biblioteca de componentes Vue.js que oferece uma solução elegante e completa para a criação de interfaces de usuário modernas e responsivas. Com um amplo conjunto de componentes prontos para uso, o Element Plus permite aos desenvolvedores agilizar o processo de desenvolvimento, fornecendo elementos visuais consistentes e interativos.

Clique [aqui](https://element-plus.org/), para acessar a documentação oficial.
</p>

### Spring Boot [![Spring Boot](https://img.shields.io/badge/Spring_Boot-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white)](https://spring.io/projects/spring-boot)

<p style="text-align: justify;">
O Spring Boot é um framework Java open source que tem como objetivo facilitar esse processo em aplicações Java. Trazendo mais agilidade para o processo de desenvolvimento com uma infinidade de ferramentas surge todos os dias visando justamente acelerar o processo de criação e implantação de soluções nos mais variados ambientes.

Clique [aqui](https://spring.io/projects/spring-boot), para acessar a documentação oficial.
</p>

##  Contribuições Pessoais ✔
<p style="text-align: justify;">
Neste projeto, desempenhei um papel essencial ao trabalhar diretamente no desenvolvimento do front-end da aplicação e no banco de dados. Minhas responsabilidades incluíram a criação do modelo DER do banco de dados e a geração do DDL correspondente, e também a criação de gráficos atráves do Charts do google.

Além disso, fiquei responsável pelo desenvolvimento da tela de login e pela implementação dos modais gerais da aplicação. Minha contribuição direta ajudou a proporcionar uma experiência fluída e intuitiva ao usuário, ao mesmo tempo em que garantia uma correta persistência dos dados necessários para o funcionamento adequado do sistema.

Esse projeto foi uma oportunidade valiosa para aprimorar minhas habilidades e adquirir experiência prática em tecnologias relevantes para a indústria da tecnologia da informação.
</p>

<details><summary>Tela Login</summary>
<img src="https://github.com/pdrMottaS/Portifolio/assets/74321890/12f0fd7e-760f-4b28-bac5-a8e88a573b2f">

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
<br>

Também fiquei responsável pela parte dos gráficos, utilizando a api do Google o google charts

<details><summary>Gráficos</summary>

<img src="https://github.com/DolphinDatabase/Cloud-In/assets/74321890/a2e5f9ff-2b5e-4270-b66e-678b0ecf13e4">

> Um trecho da tela Home com foco no desenvolvimento dos gráficos, foram feitos utilizando uma Api do próprio Google, o GoogleCharts, para sincronizar com os dados refrentes ao usuário Cliente logado no sistema.

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
<p style="text-align: justify;">
A participação nesse projeto foi de extrema importância para o meu crescimento profissional, pois representou um marco na minha trajetória ao possibilitar o trabalho simultâneo com dois frameworks simultaneamente, resultando em uma experiência prática de integração completa entre front-end e back-end. O contato com essa tecnologia foi desafiador, porém profundamente recompensador, uma vez que pude aplicar o conhecimento adquirido em projetos anteriores e impulsionar ainda mais minhas habilidades em desenvolvimento de front-end.

A experiência adquirida nesse projeto foi extremamente enriquecedora, pois permitiu-me aplicar conceitos teóricos em um contexto real, enfrentando desafios complexos e adquirindo um conhecimento mais aprofundado em desenvolvimento de aplicações web. Essa vivência consolidou meu domínio das tecnologias envolvidas e ampliou meu conjunto de habilidades, tornando-me um profissional mais completo e preparado para enfrentar projetos desafiadores no futuro.

- Desenvolver um CRUD: Sei Fazer com Autonomia.
- Desenvolvimento Front-end utilizando VueJS: Sei Fazer com Autonomia.
- Utilização do OracleCloud: Sei Fazer com Autonomia.
</p>

## Navegação Entre Projetos :link:
 
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Julius.md"> 1º Semestre: Julius - Assistente virtual criado para facilitar a sua vida financeira</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/SGBD_Health.md"> 2º Semestre: SGBD Health - Aplicação de monitoramento de SGBD com foco em performance e desempenho</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Descont0n.md"> 3° Semestre: Descont0n - Ferramenta para criação de promoções e regras de negócio de E-commerce</a></li></p>
<p align="justify" style="font-family:roboto;"><li> 4° Semestre: MCS - Sistema ERP que visa fazer a gestão dos dados fornecidos pelo usuário</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/TechNinjas.md">5° Semestre: Tech Ninjas - Sistema de automatização para fluxo de gestão dos arquivos armazenados em cloud</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/TechVision.md">6º Semestre: TechVision - Sistema de classificação e identificação geográfica de glebas</a></li>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/README.md"> Voltar para página inicial</a></li></p>

