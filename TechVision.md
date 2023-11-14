# Projeto 6: 2º Semestre de 2023

### Parceiro Acadêmico

Visiona Espacial 

![Visiona](https://github.com/Borgarelli/Portfolio-Fatec/assets/79945984/5f9a61fb-c362-4d7f-b1c1-a208ffca88f2)

### *Visiona Espacial*

### Visão do Projeto

<p style="text-align: justify;">
Propomos uma solução abrangente que envolve a coleta e o refinamento dos dados públicos do ProAgro, a reestruturação eficiente da base de dados e o desenvolvimento de um Sistema de Informação Geográfica (SIG) personalizado, fornecendo informações de forma mais simples e organizada para o usuário. Essa abordagem busca facilitar a compreensão e análise dos dados, contribuindo para melhorias nos processos internos da empresa.</p>

[<img src ="https://github.com/Borgarelli/Portfolio-Fatec/assets/79945984/71e3cfd2-da41-4e5b-bd74-d5621fb1115e"
 width="250" height="250"/>](https://github.com/TechVisionn/tech-parent "Tech Vision Repositório")

### *Tech Vision Parent*
Link do repositório do projeto: https://github.com/TechVisionn/tech-parent

## Tecnologias Utilizadas 💻

### MongoDB  [![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b?style=for-the-badge&logo=mongodb)](https://docs.mongodb.com/)

<p style="text-align: justify;">
O MongoDB é um banco de dados NoSQL de código aberto, orientado a documentos. Ele oferece flexibilidade e escalabilidade para armazenar e consultar dados, permitindo o uso de esquemas dinâmicos. Utilizado em diversas aplicações, o MongoDB simplifica o desenvolvimento ao suportar modelos de dados variados.
</p>

Clique [aqui](https://docs.mongodb.com/), para acessar a documentação oficial.

### Pandas [![Pandas](https://img.shields.io/badge/Pandas-%23150458?style=for-the-badge&logo=pandas)](https://pandas.pydata.org/)

<p style="text-align: justify";>
O Pandas é uma poderosa biblioteca de código aberto para manipulação e análise de dados em Python. Ele oferece estruturas de dados flexíveis, como DataFrames, para facilitar a limpeza, transformação e análise eficiente de conjuntos de dados. Amplamente utilizado em ciência de dados e análise, o Pandas simplifica tarefas complexas de manipulação de dados.
</p>

Clique [aqui](https://pandas.pydata.org), para acessar a documentação oficial.


### Flask [![Flask](https://img.shields.io/badge/Flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white)](http://flask.pocoo.org/)

<p style="text-align: justify;">
O Flask é um framework leve em Python para construção de aplicativos web. Onde o framework oferece diversas ferramentas para criar rapidamente aplicações web simples a complexas, seguindo o padrão de arquitetura MVC (Model-View-Controller). 
<p>

Clique [aqui](https://flask.palletsprojects.com/en/2.3.x/), para acessar a documentação oficial.


### SQL-Alchemy [![SQL-Alchemy](https://img.shields.io/badge/SQL--Alchemy-%230D6A8F.svg?style=for-the-badge&logo=sqlalchemy&logoColor=white)](https://www.sqlalchemy.org/)

<p style="text-align: justify;">
O SQL-Alchemy é uma biblioteca em Python que fornece uma abstração flexível para trabalhar com bancos de dados relacionais. Esta biblioteca permite que os desenvolvedores criem consultas SQL de maneira programática, mapeiem objetos Python para tabelas do banco de dados e gerenciem interações complexas com o banco de dados de forma eficiente.
</p>

Clique [aqui](https://docs.sqlalchemy.org/), para acessar a documentação oficial.

### React [![React](https://img.shields.io/badge/React-%2320232a?style=for-the-badge&logo=react)](https://reactjs.org/)
<p style="text-align: justify;">
O React é uma biblioteca JavaScript para construção de interfaces de usuário, desenvolvida pelo Facebook. Ele utiliza uma abordagem de programação declarativa, facilitando a criação de componentes reutilizáveis que atualizam automaticamente conforme os dados mudam, proporcionando uma experiência eficiente e responsiva para o desenvolvimento de aplicações web interativas.
</p>

Clique [aqui](https://reactjs.org), para acessar a documentação oficial.

### Microsoft-Azure [![Azure](https://img.shields.io/badge/Microsoft_Azure-%230078D4?style=for-the-badge&logo=microsoft-azure)](https://docs.microsoft.com/azure/)
<p style="text-align: justify;">
O Microsoft Azure é uma plataforma de computação em nuvem líder que oferece uma ampla gama de serviços, desde hospedagem de máquinas virtuais até inteligência artificial. Ele fornece soluções escaláveis para desenvolvimento, implantação e gerenciamento de aplicativos, além de suportar diversas linguagens de programação. Com recursos como armazenamento, análise de dados e aprendizado de máquina, o Azure é uma escolha popular para empresas modernas na nuvem.
</p>

Clique [aqui](https://docs.microsoft.com/azure/), para acessar a documentação oficial.

### PostgreSQL [![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
<p style="text-align: justify;">
O PostgreSQL é um banco de dados objeto-relacional (sem relação com linguagens de programação orientadas a objetos), em que cada coisa criada é tratada como um objeto, tais como bancos de dados, tabelas, views, triggers, etc.
</p>

Clique [aqui](https://www.postgresql.org/about/) para acessar a documentação oficial.


##  Contribuições Pessoais ✔
<p style="text-align: justify;">
Neste projeto, fui um dos responsáveis pela gestão e tratamento de dados, através da biblioteca Pandas, foi possível fazer uma leitura e conversão dos dados em csv disponibilizados pela Visiona, para essa primeira instancia e contato com esses csv, criei um script básico para a conversão e lipeza dos dados para a visualização dos mesmos

<details><summary>Script para leitura dos CSV</summary>

```kotlin
import pandas as pd
import os
import chardet

def detectar_codificacao(arquivo_csv):
    with open(arquivo_csv, 'rb') as f:
        result = chardet.detect(f.read())
        return result['encoding']

def identificar_separador_csv(arquivo_csv):
    with open(arquivo_csv, 'r', newline='') as file:
        conteudo = file.read(1024)  # Leia apenas os primeiros 1024 bytes

        # Tente identificar o separador com base em algumas pistas
        if ',' in conteudo:
            return ','
        elif ';' in conteudo:
            return ';'
        elif '\t' in conteudo:
            return '\t'
        else:
            return None  # Se não encontrar um separador conhecido, retorne None

def ler_csv_e_preencher_nulos(arquivo_csv):
    codificacao = detectar_codificacao(arquivo_csv)
    sep = identificar_separador_csv(arquivo_csv)

    if sep is None:
        print("Não foi possível identificar automaticamente o separador.")
        return

    try:
        # Tentar ler com o separador identificado
        df = pd.read_csv(arquivo_csv, encoding=codificacao, sep=sep, quotechar='"', quoting=3, on_bad_lines='skip', na_values=['NaN', 'N/A', 'NA', 'nan', 'n/a'])

        if not df.empty:
            # Remover as aspas duplas dos valores na coluna "VL_VERTICES"
            df['VL_VERTICES'] = df['VL_VERTICES'].str.strip('"')

            NU_IDENTIFICADOR = df['NU_IDENTIFICADOR']
            print(NU_IDENTIFICADOR)
        else:
            print("Arquivo CSV vazio.")
    except UnicodeDecodeError:
        print(f"Tentando com codificação {codificacao}... Não foi possível decodificar.")
    except pd.errors.ParserError:
        print(f"Não foi possível analisar o arquivo CSV com o separador '{sep}'.")

def main():
    os.system('cls')
    arquivo_csv = r"C:\Users\borga\Documents\aula_massanori\resultado_novo2 - Copia.csv"
    ler_csv_e_preencher_nulos(arquivo_csv)

if __name__ == "__main__":
    main()
```
</details>
</br>

Após ser possivel realizar uma leitura desses dados, foi necessário armazena-los e trata-los dentro da cloud, para tornar o acesso restrito e seguro, para isso trabalhei na configuração do pipeline dentro da Microsoft-Azure, que foi a principal ferramenta para armazenar esses dados, para isso o pipeline trabalha de uma maneira simples, primeiro é necessário carregar o csv dentro da azure e criar um DDL com as informações desse csv dentro do SGBD, e para isso utilizei o Postgre, depois é necessário criar uma instancia em formato Postgre_Azure e assim que criados o pipeline realiza o mapeamento da tabela dentro do cloud com seu respectivo csv.

<details><summary>Microsoft Azure Factory</summary>

</p>

<details><summary>Interface Principal</summary>
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
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/SGBD_Health.md"> 2º Semestre: SGBD Health - Aplicação de monitoramento de SGBD com foco em performance e desempenho</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Descont0n.md"> 3° Semestre: Descont0n - Ferramenta para criação de promoções e regras de negócio de E-commerce</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/MCS.md"> 4° Semestre: MCS - Sistema ERP que visa fazer a gestão dos dados fornecidos pelo usuário</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a> 5° Semestre: Tech Ninjas - Sistema de automatização para fluxo de gestão dos arquivos armazenados em cloud</a></li></p>
<p align="justify" style="font-family:roboto;"><li>6° Semestre: TechVision - Sistema de automatização para fluxo de gestão dos arquivos armazenados em cloud</li>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/README.md"> Voltar para página inicial</a></li></p>
