## Projeto 3: 2020-2


### Parceiro Acadêmico
Visiona

### Visão do Projeto

Desenvolver um sistema web que atue como um mini ETL, convertendo shapefiles (arquivos que representam formatos geográficos) em bases de dados geográficas. 
Mais especificamente, em bancos gerenciados pelo PostgreSQL com o apoio da extensão PostGIS.

A sigla ETL (Extract, transform and load) resume bem a tarefa que possuíamos em mãos.

A ferramenta desenvolvida pela minha equipe, a VisGeo, se baseava em uma plataforma web onde um usuário poderia realizar a carga de dados geográficos
contidos em shapefiles em um banco dedados que possuísse suporte para este tipo de dado. Ou seja, nossa ferramenta deveria extrair os dados enviados pelo usuário,
tranformá-los no formato compatível com o banco de dados que receberia aquele lote de informações, e realizar a carga dos dados nesta base de dados.

O caminho inverso também deveria ser válido, permitindo converter a base de dados geográfica em arquivos que constituem um shapefile.

Link do repositório do projeto: https://github.com/justhenrique/SPC-projeto-integrador

### Tecnologias adotadas na solução

#### GeoPandas

O GeoPandas é uma biblioteca de análise de dados geográficos. Com ela, é possível trabalhar com diversas fontes de dados geográficos, incluindo shapefiles e 
bases de dados geográficos, que eram as duas fontes necessárias para os requisitos do projeto.

Com o GeoPandas foi possível extrair, realizar conversões e ajustes necessários nos shapefiles, e realizar as cargas necessárias na base de dados selecionada 
pelo usuário da ferramenta.

Para saber mais sobre o GeoPandas, acesse sua [página oficial.](https://geopandas.org/)


#### Flask

Neste projeto os membros de nossa equipe obtiveram o primeiro contato com um framework web, e o utilizado neste momento foi o Flask.

O Flask é um microframework web, que funciona com base na linguagem de programação Python. O radical "micro" em "microframework" é empregado pois o escopo base 
do Flask é enxuto. Ou seja, o Flask não determina ou limita o modo com o qual o seu projeto web será construído. Ele falicita a implamentação básica de um sistema web, permitindo diversos modos de desenvolvimento. Por ser leve, enxuto e dinâmico no desenvolvimento de projetos, ele recebe esta denominação.

Saiba mais sobre o Flask em sua [página oficial.](https://flask.palletsprojects.com/en/2.0.x/).

O Flask foi um dos frameworks utilizados no sistema. Nossa ferramenta trabalhou com dois serviços principais. Um deles era responsável pelo serviço de ETL, que era o
núcleo de nossa ferramenta. E outro framework foi responsável por disponibilizar o serviço de criação e autenticação de usuários, outro requisito de nosso sistema.

#### Express

O Express é um microframework web, que roda sobre o motor do Node.js
O Express é uma ótima solução para a construção de sistemas web, por meio dele, os serviços de autenticação e criação de usuários foram disponibilizados para nossa aplicação.


### Contribuições pessoais

Fui responsável pela criação dos algoritmos de fluxo de conversão do shapefile em uma tabela compatível com bases de dados geográficos.
Para isso, foi necessário estudar sobre uma área completamente nova.



### Aprendizados Efetivos HS

A UDA Brasil foi primeiro sistema web com o qual trabalhei. Em seu desenvolvimento, obtive meu primeiro contato com conceitos bases para todo profissional desenvolvedor de software. Os aprendizados inéditos foram diversos, que necessitam ser citados aqui:

- O que é o protocolo HTTP;
- O que é uma requisição GET, POST, PUT e quais são as diferentes destes verbos;
- Como funciona a comunicação de uma página de um usuário com a lógica interna de um sistema;
- O que é um JSON e como ele funciona na comunicação de sistemas web;
- O que é um framework web e qual sua utilidade na construção de sistemas.


Além destes itens importantes que foram citados acima, outros aprendizados importantes precisam ser mencionados:

Durante o desenvolvimento do projeto, a performance do sistema foi uma questão central em seu desenvolvimento.
Possuíamos uma base de dados minimamente volumosa, e precisávamos calcular diversos fatores de todos os seus registros. Com isso, precisávamos pensar em formas mais eficientes em processamento para garantir uma resposta rápida e confiável ao nosso usuário final. A evolução nos algoritmos de análise de dados com o passar do projeto é algo que foi de grande valia para a nossa formação como profissionais desenvolvedores.

No mais, o conhecimento adquirido neste projeto pode ser resumido da seguinte forma:

- Criação de uma API HTTP que gerencia requests e respostas para um cliente: sei fazer com autonomia

- Importação de dados de diferentes fontes e análises gerais sobre o conteúdo importado: sei fazer com autonomia
