# Projeto 5: 1º Semestre de 2023

### Parceiro Acadêmico

MidAllº [B] 

![MidAll](https://user-images.githubusercontent.com/79945984/225166828-fd8d6942-68e5-4c26-9466-06bc7b08e0d0.png)

### *MidAllº [B]*

### Visão do Projeto

<p align="justify">
Este projeto consiste em automatizar a jornada de controle de seus arquivos armazenados em uma plataforma de vídeos. Onde a aplicação  transferindo-os para a nuvem, por meio do desenvolvimento de um aplicativo como serviço, com apenas um menu de configuração para o usuário, que terá os parâmetros necessários para o processo de serviço de download de forma automática, gerando alertas em caso de erro no processamento. Fica responsável por salvar os metadados do arquivo para construir um painel de controle para monitorar a execução do serviço e posteriormente analisar resultados e indicadores.
</p>

[<img src ="https://github.com/TechNinjass/midall-parent/blob/main/docs/Images/logo-techNinjass.png" width="250" height="250"/>](https://github.com/TechNinjass/midall-parent "Tech Ninjas Repositório")


Link do repositório do projeto: https://github.com/TechNinjass/midall-parent

## Tecnologias Utilizadas 💻

### Vue [![Vue.js](https://img.shields.io/badge/Vue.js-%234FC08D.svg?style=for-the-badge&logo=vue.js&logoColor=white)](https://vuejs.org/)

Vue.js é um framework JavaScript de código aberto para a criação de interfaces de usuário reativas e eficientes.

Clique [aqui](https://vuejs.org/), para acessar a documentação oficial.

### Tailwind css  [![Tailwind CSS](https://img.shields.io/badge/Built_with-Tailwind_CSS-38B2AC?logo=tailwind-css&style=flat-square)](https://tailwindcss.com/)

O Tailwind CSS é um framework de CSS que usa classes utilitárias para estilizar diretamente o HTML, agilizando o desenvolvimento front-end. Este framework oferece uma ampla gama de classes pré-definidas para estilos, margens, cores e responsividade, permitindo criar interfaces atraentes de forma rápida e flexível.

Clique [aqui](https://element-plus.org/), para acessar a documentação oficial.

### Flask [![Flask](https://img.shields.io/badge/Flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white)](http://flask.pocoo.org/)


O Flask é um framework leve em Python para construção de aplicativos web. Onde o framework oferece diversas ferramentas para criar rapidamente aplicações web simples a complexas, seguindo o padrão de arquitetura MVC (Model-View-Controller). 

Clique [aqui](https://flask.palletsprojects.com/en/2.3.x/), para acessar a documentação oficial.


### SQL-Alchemy [![SQL-Alchemy](https://img.shields.io/badge/SQL--Alchemy-%230D6A8F.svg?style=for-the-badge&logo=sqlalchemy&logoColor=white)](https://www.sqlalchemy.org/)

O SQL-Alchemy é uma biblioteca em Python que fornece uma abstração flexível para trabalhar com bancos de dados relacionais. Esta biblioteca permite que os desenvolvedores criem consultas SQL de maneira programática, mapeiem objetos Python para tabelas do banco de dados e gerenciem interações complexas com o banco de dados de forma eficiente.

Clique [aqui](https://docs.sqlalchemy.org/), para acessar a documentação oficial.


## Contribuições pessoais ✔

Nesta empreitada, assumi a responsabilidade pela concepção e desenvolvimento da interface gráfica. Empreguei o Vue.js 3 como um dos pontos principais da aplicação. A configuração das rotas realizei utilizando a bilioteca vue-router, e a estlização de componentes mais dinâmicos e personalizados do projeto estruturei utilizando o Tailwind CSS. Também realizei a tarefa da criação das estruturas de dados em Python mais conhecidas como models, e para realizar está tarefa utilizei à biblioteca SQL-Alchemy.

Este projeto configurou-se como uma notável oportunidade para aprimorar minhas competências como um desenvolvedor e cultivar uma experiência prática embasada em tecnologias que cada vez mais vem se mostrando mais requisitadas. Nesse âmbito, pude expandir meu entendimento e aplicação das ferramentas essenciais, reforçando minha capacidade de oferecer soluções inovadoras em possiveis novos futuros projetos desafiadores.

<details><summary>Interface principal</summary>
<img src="https://github.com/Borgarelli/Portfolio-Fatec/assets/79945984/e4cc6f49-8251-45cd-ae87-42ec1242909e">

> Essa é a interface principal da aplicação, onde utilizando toda a versatilidade do Vue, todos os elementos que a compõem estão componentizados e separados corretamente,e também otimizados e aplicados a coordenação de rotas utilizando o vue-router

```kotlin
<template>
  <div class="fundo">
    <div id="appView">
      <Cabecalho></Cabecalho>
      <div class="button-container">
        <router-link to="Configuracoes">
          <button class="my-button">
            <img src="../assets/config.png" alt="listagem" class="button-icon">
            <span class="button-text config">CONFIGURAÇÕES</span>
          </button>
        </router-link>
        <router-link to="tabela">
          <button class="my-button">
            <img src="../assets/listagem.png" alt="upload" class="button-icon">
            <span class="button-text">LISTAGEM DE ARQUIVOS</span>
          </button>
       </router-link>
        <router-link to="">
          <button class="my-button">
            <img src="../assets/grafico.png" alt="dashboard" class="button-icon">
            <span class="button-text config">DASHBOARD</span>
          </button>
       </router-link>
      </div>
      <video width="320" height="240" autoplay loop muted class="gif-ninja">
        <source src="../assets/gifDevNinja.mp4" type="video/mp4" />
      </video>
  </div>
</div>
</template>

<style scoped>
    .button-container {
        position: relative;
        height: 70vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: row;
        gap:200px;
    }

    .my-button {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 300px;
        height: 310px;
        background-color: white;
        border-radius: 50px;
        color: white;
        font-size: 30px;
        font-weight: bold;
    }

    .my-button:hover {
      transform: scale(1.1);
      transition: 200ms linear;
    }

    .button-icon {
        width: 170px;
        height: 170px;
        padding-top: 40px;
    }

    .button-text {
        color: hwb(212 12% 38%);
        display: inline-block;
        white-space: wrap;
        padding-top: 20px;
        padding-right: 30px;
        padding-bottom: 30px;
        padding-left: 30px;
    }

    .fundo {
        position: absolute;
        background:  #B1D4E0;
        height: 100%;
        width: 100%;
    }

    .config {
      margin-top: 25px;
    }

    .gif-ninja {
      margin-left: 87%;
      margin-top: -4%;
      width: 12%;
    }
</style>

<script>
  import Cabecalho from '../components/Cabecalho.vue';
  export default {
    name: 'HomeView',

    components: {
      Cabecalho
    }
  }
</script> 
```
</details>

Modelagem das Models utilizando o SQL-Alchemy

<details><summary>Models</summary>

> Utilizando o SQL-Alchemy assim foram estruturadas as models para gerar nosso banco de dados, e apartir dele armazenar todos os dados e metadados exigidos.

```kotlin
from flaskr.db import db_instance

class Files(db_instance.Model):
    File_Id = db_instance.Column(db_instance.Integer, primary_key=True)
    Size_Files = db_instance.Column(db_instance.Integer, nullable=False)
    Format = db_instance.Column(db_instance.String(30), nullable=True)
    Name = db_instance.Column(db_instance.String(254), nullable=False)
    Date_Upload = db_instance.Column(db_instance.Date, nullable=False)
    Clouds_Fk = db_instance.Column(db_instance.Integer, db_instance.ForeignKey('cloud.Cloud_Id'))

class Network_Data(db_instance.Model):
    Network_Id = db_instance.Column(db_instance.Integer, primary_key=True)
    Speed_Upload = db_instance.Column(db_instance.Integer, nullable=False)
    Data_Used = db_instance.Column(db_instance.Date, nullable=False)
    Size_Files_Transf = db_instance.Column(db_instance.Integer, nullable=False)
    Time_Transfer = db_instance.Column(db_instance.Time, nullable=True)
    Data_Transfer = db_instance.Column(db_instance.Date, nullable=True)
    Cloud_Fk = db_instance.Column(db_instance.Integer, db_instance.ForeignKey('cloud.Cloud_Id'))

class Configuration(db_instance.Model):
    Config_Id = db_instance.Column(db_instance.Integer, primary_key=True)
    Limit_Size_Transfer = db_instance.Column(db_instance.Integer, nullable=True)
    Limit_Size_Files_Send = db_instance.Column(db_instance.Integer, nullable=True)
    Time_Start_Verify = db_instance.Column(db_instance.Time, nullable=False)
    Time_End_Verify = db_instance.Column(db_instance.Time, nullable=True)
    Interval_Verify_Files = db_instance.Column(db_instance.Time, nullable=False)
    Date_Update = db_instance.Column(db_instance.Date, nullable=False)
    Path_File_Origin = db_instance.Column(db_instance.String(254), nullable=True)
    Path_File_Destiny = db_instance.Column(db_instance.String(254), nullable=True)
    Cloud_Id = db_instance.Column(db_instance.Integer, db_instance.ForeignKey('cloud.Cloud_Id'), nullable=True)
    cloud = db_instance.relationship('Cloud', backref=db_instance.backref('configurations', lazy=True))

class Cloud(db_instance.Model):
    Cloud_Id = db_instance.Column(db_instance.Integer, primary_key=True)
    Url_Cloud_Destiny = db_instance.Column(db_instance.String(254), nullable=False)
    Url_Cloud_Origin = db_instance.Column(db_instance.String(254), nullable=False)
    Secret_Cloud_Origin = db_instance.Column(db_instance.String(254), nullable=False)
    Secret_Cloud_Destiny = db_instance.Column(db_instance.String(254), nullable=False)
    configurations = db_instance.relationship('Configuration', backref=db_instance.backref('cloud', lazy=True))
    network_data = db_instance.relationship('Network_Data', backref=db_instance.backref('cloud', lazy=True))
    files = db_instance.relationship('Files', backref=db_instance.backref('cloud', lazy=True))
```
</details>

## Aprendizados Efetivos ![Aprendizados efetivos](https://img.shields.io/badge/Aprendizados%20efetivos-100%25-brightgreen?style=for-the-badge)
Este projeto representou uma oportunidade de aprendizado significativa, durante a qual fui introduzido ao conceito de DevOps, um ecossistema substancialmente diferente da minha familiaridade prévia. Este novo domínio me permitiu explorar a computação em nuvem, engajando-me na transferência eficiente de arquivos entre serviços de nuvem distintos. Adotando a metodologia GitFlow, assumi a responsabilidade de incorporá-la ao projeto, aplicando seus princípios de forma a estabelecer nossa própria abordagem personalizada.

A experiência acumulada ao longo deste projeto foi profundamente enriquecedora. Tive a oportunidade de aplicar conceitos teóricos em um contexto prático, enfrentando desafios intrincados que ampliaram meu entendimento do desenvolvimento de aplicações web. Esta vivência consolida minha proficiência nas tecnologias empregadas, enquanto expande meu repertório de habilidades. Dessa forma, estou mais bem preparado para enfrentar com confiança projetos desafiadores no futuro.

- Aplicar conceitos de DevOps - GitFlow: Sei Fazer com Autonomia.
- Criação das models utilizando o SQL-Alchemy: Sei Fazer com Autonomia.
- Desenvolvimento da interface utilizando Vue js 3: Sei Fazer com Autonomia. 

## Navegação Entre Projetos :link:
 
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Julius.md"> 1º Semestre: Julius - Assistente virtual criado para facilitar a sua vida financeira</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/SGBD_Health.md"> 2º Semestre: SGBD Health - Aplicação de monitoramento de SGBD, foco em performance e desempenho</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Descont0n.md"> 3° Semestre: Descont0n - Ferramenta para criação de promoções e regras de negócio de E-commerce</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/MCS.md"> 4° Semestre: MCS - Sistema ERP que visa fazer a gestão dos dados fornecidos pelo usuário</a></li></p>
<p align="justify" style="font-family:roboto;"><li> 5° Semestre: TECH NINJAS - Sistema de automatização para fluxo de gestão dos arquivos armazenados em cloud
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/README.md"> Voltar para página inicial</a></li></p>
