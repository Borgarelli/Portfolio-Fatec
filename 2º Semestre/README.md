## Projeto 2: 2020-1


### Parceiro Acadêmico
SPC Brasil

### Visão do Projeto

A proposta inicial do projeto era desenvolver uma ferramenta de análise de dados a partir de dados de compra e operações de crédito de clientes. 
Os dados, obviamente, eram exemplos descaracterizados para fins acadêmicos.
A visão do produto a ser criado não foi definida pela empresa. A intenção era de, a partir dos dados providos, que montássemos e sugeríssemos produtos válidos 
para sua operação.

O projeto desenvolvimento por minha equipe, a UDA Brasil, possuiu o seguinte objetivo:

Criar uma ferramenta Web de análise da qualidade dos dados, rankeando as fontes de dados de acordo com a consistência, completude e confiabilidade
dos lotes enviados.

Link do repositório do projeto: https://github.com/justhenrique/SPC-projeto-integrador

### Tecnologias adotadas na solução

#### Flask

Neste projeto os membros de nossa equipe obtiveram o primeiro contato com um framework web, e o utilizado neste momento foi o Flask.

O Flask é um microframework web, que funciona com base na linguagem de programação Python. O radical "micro" em "microframework" é empregado pois o escopo base 
do Flask é enxuto. Ou seja, o Flask não determina ou limita o modo com o qual o seu projeto web será construído. Ele falicita a implamentação básica de um sistema web, permitindo diversos modos de desenvolvimento. Por ser leve, enxuto e dinâmico no desenvolvimento de projetos, ele recebe esta denominação.
Saiba mais sobre o Flask em sua [página oficial.](https://flask.palletsprojects.com/en/2.0.x/)

Com o Flask, foram criadas as rotas HTTP que o nosso sistema consumiu. Além disso, em auxílio com a engine de renderização de templates, a
[Jinja2](https://jinja.palletsprojects.com/en/3.0.x/), as páginas de nossa plataforma foram renderizadas para o usuário final.


#### Pandas

O coração do nosso sistema, responsável por facilitar a extração, tratamento e análise dos dados, foi construído com o auxílio da conhecida biblioteca [Pandas](https://pandas.pydata.org/)

O Pandas é uma biblioteca para a linguagem de programação Python, que provê uma série de ferramentas para a extração, conversão e análise de dados. Com o auxílio 
dela, os algoritmos de análise da qualidade dos dados foi construída, o que permitiu que nossa ferramenta pudesse entregar seu principal valor. O ranking das 
fontes por meio da qualidade dos dados enviados por ela.


### Contribuições pessoais

Fui responsável por vários dos scripts que análisavam os lotes de dados de acordo com critérios determinados pela entidade parceira.

Os itens utilizados para determinar a qualidade dos dados era:

- Completude: o quão completos eram os dados. A base possui um alto índice de dados em brancos ou nulos?
- Confiabilidade: os valores preenchidos nos campos de um lote de dados não foram truncados? Eles fazem sentido em seu respectivo contexto?
- Consistência: o valor preenchido em cada um dos campos é consistente com o seu propósito? Os valores referentes à nomes, por exemplo, não estão preenchidos por número ou qualquer outro dado incompatível com um nome?

Com base nestes pilares, iniciei a construção dos algoritmos. 

Com métodos de extração e leituras de dados da biblioteca Pandas, conseguimos converter os dados fornecidos no formato de arquivo .xlsx em DataFrames.

DataFrames são objetos internos da biblioteca Pandas. Eles comportam dados em formato bidimensional, com linhas e colunas, compatível com o formato da fonte, em planilhas (arquivos XLSX).

Com o simples código abaixo, era possível importar um arquivo Excel e convertê-lo em um DataFrame do Pandas.

```code
import pandas as pd
df = pd.read_excel('meuArquivoExcel.xlsx')
```

Com as duas linhas acima, o objeto identificado por "df" é um DataFrame Pandas. Nele, é possível utilizar um arsenal robusto que permite filtrar, contabilizar e tratar dados incompletos, inconsistêntes e analisar sua integridade.

Com base nisso o ranking, feature principal da nossa ferramenta, foi construído. Ele pode ser visto abaixo:

![Ranking-UDA-Brasil](https://user-images.githubusercontent.com/45850297/138625070-8d960faf-d4b6-482b-8887-ffb30a7c6ac3.png)

Nosso cliente recebe dados de inúmeras fontes. Com a UDA Brasil, ele poderia visualizar se alguma das fontes estava pecando na qualidade dos dados, e em qual ponto deveria melhorar/corrigir problemas.


### Aprendizados Efetivos HS

A UDA Brasil foi primeiro sistema web com o qual trabalhei. Em seu desenvolvimento, obtive meu primeiro contato com conceitos bases para todo profissional desenvolvedor de software. Os aprendizados inéditos foram diversos, que necessitam ser citados aqui:

- O que é o protocolo HTTP;
- O que é uma requisição GET, POST, PUT e quais são as diferentes destes verbos;
- Como funciona a comunicação de uma página de um usuário com a lógica interna de um sistema;
- O que é um JSON e como ele funciona na comunicação de sistemas web;
- O que é um framework web e qual sua utilidade na construção de sistemas.


Além destes itens importantes que foram citados aqui, outros aprendizados importantes precisam ser mencionados.

Durante o desenvolvimento do projeto, a performance do sistema foi uma questão central em seu desenvolvimento.
Possuíamos uma base de dados minimamente volumosa, e precisávamos calcular diversos fatores de todos os seus registros. Com isso, precisávamos pensar em formas mais eficientes em processamento para garantir uma resposta rápida e confiável ao nosso usuário final. A evolução nos algoritmos de análise de dados com o passar do projeto é algo que foi de grande valia para a nossa formação como profissionais desenvolvedores.

No mais, os seguintes itens de aprendizado podem resumir o que foi aprendido:

- Criação de uma API HTTP que gerencia requests e respostas para um cliente: sei fazer com autonomia

- Importação de dados de diferentes fontes e análises gerais sobre o conteúdo importado: sei fazer com autonomia
