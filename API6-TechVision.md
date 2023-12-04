# Projeto 6: 2º Semestre de 2023

### Parceiro Acadêmico

Visiona Espacial 

![Visiona](https://github.com/Borgarelli/Portfolio-Fatec/assets/79945984/5f9a61fb-c362-4d7f-b1c1-a208ffca88f2)

### *Visiona Espacial*

### Visão do Projeto

<p style="text-align: justify;">
O projeto tem como objetivo a instauração de um Sistema de Informação Geográfica (SIG) com o propósito de aprimorar a eficácia das análises e otimizar os procedimentos internos. Embora os dados necessários estejam acessíveis no ProAgro, um programa do governo federal voltado ao financiamento agrícola para pequenos e médios agricultores brasileiros, desafios significativos surgem devido à falta de organização, à presença de informações sensíveis e à sobrecarga de dados.

A ideia é apresentar uma solução completa, envolvendo a coleta e o aprimoramento dos dados públicos do ProAgro, a eficiente reestruturação da base de dados e o desenvolvimento de um SIG personalizado. Esse sistema tem como intuito simplificar e organizar as informações, proporcionando aos usuários uma compreensão mais acessível e facilitando a análise dos dados. Destaca-se a organização do banco de dados público do ProAgro para possibilitar consultas e análises rápidas no âmbito do Sistema de Informações Geográficas.</p>

[<img src ="https://github.com/Borgarelli/Portfolio-Fatec/assets/79945984/71e3cfd2-da41-4e5b-bd74-d5621fb1115e"
 width="250" height="250"/>](https://github.com/TechVisionn/tech-parent "Tech Vision Repositório")

### *Tech Vision Parent*
Link do repositório do projeto: https://github.com/TechVisionn/tech-parent

## Tecnologias Utilizadas 💻

### MongoDB  [![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b?style=for-the-badge&logo=mongodb)](https://docs.mongodb.com/)

<p style="text-align: justify;">
O MongoDB é um banco de dados NoSQL de código aberto, orientado a documentos, oferece flexibilidade e escalabilidade para armazenar e consultar dados, permitindo o uso de esquemas dinâmicos e utilizado em diversas aplicações, para simplificar o desenvolvimento ao suportar modelos de dados variados.
</p>

Clique [aqui](https://docs.mongodb.com/), para acessar a documentação oficial.

### Pandas [![Pandas](https://img.shields.io/badge/Pandas-%23150458?style=for-the-badge&logo=pandas)](https://pandas.pydata.org/)

<p style="text-align: justify";>
O Pandas é uma poderosa biblioteca de código aberto para manipulação e análise de dados em Python, oferece estruturas de dados flexíveis, como DataFrames, para facilitar a limpeza, transformação e análise eficiente de conjuntos de dados.
</p>

Clique [aqui](https://pandas.pydata.org), para acessar a documentação oficial.


### Flask [![Flask](https://img.shields.io/badge/Flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white)](http://flask.pocoo.org/)

<p style="text-align: justify;">
O Flask é um framework leve em Python para construção de aplicativos web. O framework oferece diversas ferramentas para criar rapidamente aplicações web simples a complexas, seguindo o padrão de arquitetura MVC (Model-View-Controller). 
<p>

Clique [aqui](https://flask.palletsprojects.com/en/2.3.x/), para acessar a documentação oficial.


### SQL-Alchemy [![SQL-Alchemy](https://img.shields.io/badge/SQL--Alchemy-%230D6A8F.svg?style=for-the-badge&logo=sqlalchemy&logoColor=white)](https://www.sqlalchemy.org/)

<p style="text-align: justify;">
O SQL-Alchemy é uma biblioteca em Python que fornece uma abstração flexível para trabalhar com bancos de dados relacionais. E permite que os desenvolvedores criem consultas SQL de maneira programática, mapeiem objetos Python para tabelas do banco de dados e gerenciem interações complexas com o banco de dados de forma eficiente.
</p>

Clique [aqui](https://docs.sqlalchemy.org/), para acessar a documentação oficial.

### React [![React](https://img.shields.io/badge/React-%2320232a?style=for-the-badge&logo=react)](https://reactjs.org/)
<p style="text-align: justify;">
O React é uma biblioteca JavaScript para construção de interfaces de usuário, desenvolvida pelo Facebook. E utiliza uma abordagem de programação declarativa, facilitando a criação de componentes reutilizáveis que atualizam automaticamente conforme os dados mudam, proporcionando uma experiência eficiente e responsiva para o desenvolvimento de aplicações web interativas.
</p>

Clique [aqui](https://reactjs.org), para acessar a documentação oficial.

### Microsoft-Azure [![Azure](https://img.shields.io/badge/Microsoft_Azure-%230078D4?style=for-the-badge&logo=microsoft-azure)](https://docs.microsoft.com/azure/)
<p style="text-align: justify;">
O Microsoft Azure é uma plataforma de computação em nuvem líder que oferece uma ampla gama de serviços, desde hospedagem de máquinas virtuais até inteligência artificial. E fornece soluções escaláveis para desenvolvimento, implantação e gerenciamento de aplicativos, além de suportar diversas linguagens de programação. Com recursos como armazenamento, análise de dados e aprendizado de máquina, o Azure é uma escolha popular para empresas modernas na nuvem.
</p>

Clique [aqui](https://docs.microsoft.com/azure/), para acessar a documentação oficial.

### PostgreSQL [![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
<p style="text-align: justify;">
O PostgreSQL é um banco de dados objeto-relacional (sem relação com linguagens de programação orientadas a objetos), em que cada coisa criada é tratada como um objeto, tais como bancos de dados, tabelas, views, triggers, etc.
</p>

Clique [aqui](https://www.postgresql.org/about/) para acessar a documentação oficial.


##  Contribuições Pessoais ✔
<p style="text-align: justify;">
Neste projeto, desempenhei um papel fundamental na gestão e tratamento de dados. Utilizando a biblioteca Pandas, realizei a leitura e conversão dos dados em formato CSV fornecidos pela Visiona. Para essa primeira interação com os CSVs, desenvolvi um script essencial para a conversão e limpeza dos dados, visando facilitar a posterior visualização e análise.

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

Após a bem-sucedida leitura dos dados, surgiu a necessidade de armazená-los de forma segura na nuvem. Para alcançar esse objetivo, concentrei meus esforços na configuração de um pipeline na plataforma Microsoft Azure, que se revelou a ferramenta ideal para a gestão desses dados. O pipeline, de funcionamento intuitivo, inicialmente carrega o CSV para a Azure e, em seguida, cria um Data Definition Language (DDL) contendo as informações do CSV no Sistema de Gerenciamento de Banco de Dados (SGBD). Para essa etapa, contei com a eficiência do WorkBench. Posteriormente, o pipeline realiza a vinculação da tabela na nuvem com seu respectivo CSV, estabelecendo uma infraestrutura que assegura o acesso restrito e seguro aos dados.

<details><summary>Microsoft Azure Factory</summary>

 > Esse é o Microsft Azure Factory, aqui é realizado todo o processo da pipeline, que envolve desde armazenar o csv, criar a instância em Workbench-Azure e é mapeado todos os dados de seus respectivos CSV

<img src="https://github.com/Borgarelli/Portfolio-Fatec/assets/79945984/06ae6679-65e9-4d95-a09e-f8f3b08bc426">

</details>
</br>

Realizado o armazenamento dos dados de maneira eficaz, foi necessário realizar uma procedure para facilitar para o controle financeiro de todos os csv para facilitar em no calculo financeiro de cada gleba dentro do SGBD

<details><summary>Procedure</summary>

```kotlin
BEGIN
select 
	
    S5.VL_ALIQ_PROAGRO as Aliquota,
    S5.VL_JUROS as Juros,
	S5.VL_PRESTACAO_INVESTIMENTO as Prestacao,
    S5.VL_PREV_PROD as Previsao_Produto,
    S5.VL_QUANTIDADE as Quantidade, 
	S5.VL_RECEITA_BRUTA_ESPERADA as Receita_Bruta,
    S5.VL_PARC_CREDITO as Parcelado_Credito,
    S5.VL_REC_PROPRIO as Recebido_Proprio,
    S5.VL_PERC_RISCO_STN as Percentual_Risco,
    S5.VL_PERC_RISCO_FUNDO_CONST as Percentual_Fundo,
    S5.VL_REC_PROPRIO_SRV as Proprio_Srv,
    S5.VL_AREA_FINANC as Area_Financia,
    SD.VL_MEDIO_DIARIO_VINCENDO as Medio_Diario,
    SD.VL_ULTIMO_DIA as Ultimo_Dia,
    SD.VL_MEDIO_DIARIO as Media_Diaria,
    SL.LIR_VL_LIBERADO as Valor_Liberado,
    SJ.VL_RECEITAS_CONSIDERADAS as Receitas_Consideras,
    SJ.VL_COBERTURA_ANT_REC_PROPRIOS as Cobertura_Proprios,
    SJ.VL_DEMAIS_DESPESAS_COMPROV_PERD as Despesas,
    SJ.VL_CRED_CUSTEIO_USADO as Credito_Custeio,
    SJ.VL_DEMAIS_DESP_ANT_COMP_PER as Demais_Despesas,
    SJ.VL_REC_PROP_USADO as Proprio_Usado,
    SJ.VL_COB_ANT_GARANTIA_RENDA_MIN as Renda_Minima,
    SJ.VL_PERDAS_NAO_AMPARADAS as Nao_Amaparadas,
    SJ.VL_ENCARGOS_SOB_CREDITO as Encargos_Credito,
    SJ.VL_PERC_REDUTOR_COBERTURA as Redutor_Cobertura,
    SJ.VL_REMU_ANT_ENCARG_COMP_PERDAS as Remuneracao,
    SJ.VL_COBERTURA_ANT_CREDITO_CUSTEIO as Cobertura_Credito,
    SP.vl_atual as Valor_Atual,
    SP.vl_base as Valor_Base,
    SP.vl_pago as Valor_Pago,
    SP.vl_imposto as Valor_Imposto
    
    
from 
	techdata.saida5 S5 
    LEFT JOIN techvision.sicor_saldos SD on SD.REF_BACEN = S5.REF_BACEN
    LEFT JOIN techvision.sicor_liberacao_recursos SL on SL.REF_BACEN = S5.REF_BACEN
    LEFT JOIN techvision.sumula_julgamento SJ on SJ.REF_BACEN = S5.REF_BACEN
    LEFT JOIN techvision.sicor_parcelas_proagro SP on SP.REF_BACEN = S5.REF_BACEN
limit 10;
END
```
</details>
</br>

E por fim, a modelagem relacional de como está sendo realizado a colheita das tabelas para a formação das glebas e retornar na aplicação
<details><summary>Glebas</summary>

>Modelo relacional do retorno das tabelas responsáveis por compor as glebas
<img src="https://github.com/Borgarelli/Portfolio-Fatec/assets/79945984/cafd106f-6f20-4661-b45f-519ff20e98c0">

O modelo foi gerado com base nessa query
```kotlin
     def generete_query_to_pdf(self, ref_bacen):
         query = text("""
                 SELECT
                     GlebaInfo.Numero_RefBacen,
                     GlebaInfo.Numero_Ordem,
                     GlebaInfo.Cod_Identificador_Gleba,
                     GlebaInfo.Numero_Gleba,
                     GlebaInfo.Altitute,
                     GlebaInfo.NU_INDICE_PONTO,
                     GlebaInfo.Coordenas,
                     S5.DT_EMISSAO AS DATA_EMISSAO_REFBACEN,
                     CASE 
                         WHEN S5.CD_ESTADO = 'SP' THEN 'São Paulo'
                         ELSE S5.CD_ESTADO 
                     END AS ESTADO,
                     S5.CD_TIPO_SEGURO AS TIPO_SEGURO,
                     S5.DT_FIM_PLANTIO AS DATA_PLANTIO,
                     S5.CD_TIPO_IRRIGACAO AS TIPO_IRRIGACAO,
                     S5.VL_ALIQ_PROAGRO AS VALOR_ALIQUOTA,
                     S5.CD_TIPO_CULTIVO AS TIPO_CULTIVO,
                     S5.CD_TIPO_GRAO_SEMENTE AS TIPO_GRAO,
                     S5.VL_JUROS AS JUROS_INVESTIMENTO,
                     S5.VL_RECEITA_BRUTA_ESPERADA AS RECEITA_BRUTA_ESTIMADA,
                     S5.DT_FIM_COLHEITA AS DATA_FIM_COLHEITA,
                     S5.VL_PERC_CUSTO_EFET_TOTAL AS CUSTO_TOTAL
                 FROM
                 (SELECT 
                     MAX(REF_BACEN) AS Numero_RefBacen, 
                     MAX(NU_ORDEM) AS Numero_Ordem, 
                     MAX(NU_IDENTIFICADOR) AS Cod_Identificador_Gleba, 
                     MAX(NU_INDICE_GLEBA) AS Numero_Gleba,
                     MAX(CGL_VL_ALTITUDE) AS Altitute,
                     MAX(NU_INDICE_PONTO) AS NU_INDICE_PONTO,
                     CONCAT('MULTIPOINT(', GROUP_CONCAT(CONCAT(REPLACE(VL_LATITUDE, ',', '.'), ' ', REPLACE(VL_LONGITUDE, ',', '.')) SEPARATOR ', '), ')') AS Coordenas
                 FROM glebas_sp
                 WHERE REF_BACEN = :ref_bacen) AS GlebaInfo
                 JOIN saida5 S5 ON S5.REF_BACEN = :ref_bacen limit 1;""")
```
</details>
</p>



## Aprendizados Efetivos ![Aprendizados efetivos](https://img.shields.io/badge/Aprendizados%20efetivos-100%25-brightgreen?style=for-the-badge)

Essa experiência foi enriquecedora, proporcionando aprendizados práticos e efetivos. A gestão de dados com Pandas ampliou minha habilidade na manipulação eficiente de conjuntos de dados complexos, enquanto a configuração de pipelines na Microsoft Azure consolidou meu entendimento sobre a importância da segurança e organização na armazenagem de dados na nuvem.

A integração de ferramentas como o WorkBench para a criação de instâncias no formato WorkBench_Azure revelou-se uma prática valiosa, demonstrando a sinergia entre diferentes tecnologias para alcançar objetivos específicos. Essa jornada contribuiu significativamente para o aprimoramento das minhas competências em ciência de dados e gestão de infraestrutura na nuvem.

- Estruturação do banco de dados: Sei Fazer com Autonomia.
- Utilização da plataforma Azure Cloud: Sei Fazer com Autonomia.
- Utilização da biblioteca pandas para gestão dos arquivos csv: Sei Fazer com Autonomia. 

## Navegação Entre Projetos :link:
 
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Julius.md"> 1º Semestre: Julius - Assistente virtual criado para facilitar a sua vida financeira</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/SGBD_Health.md"> 2º Semestre: SGBD Health - Aplicação de monitoramento de SGBD com foco em performance e desempenho</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Descont0n.md"> 3° Semestre: Descont0n - Ferramenta para criação de promoções e regras de negócio de E-commerce</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/MCS.md"> 4° Semestre: MCS - Sistema ERP que visa fazer a gestão dos dados fornecidos pelo usuário</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/TechNinjas.md">5° Semestre: Tech Ninjas - Sistema de automatização para fluxo de gestão dos arquivos armazenados em cloud</a></li></p>
<p align="justify" style="font-family:roboto;"><li>6º Semestre: TechVision - Sistema de classificação e identificação geográfica de glebas</li>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/README.md"> Voltar para página inicial</a></li></p>
