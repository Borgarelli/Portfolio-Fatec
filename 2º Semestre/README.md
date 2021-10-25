## Projeto 2: 2020-1


### Parceiro Acadêmico
SPC Brasil

### Visão do Projeto

A proposta inicial do projeto era desenvolver uma ferramenta de análise de dados a partir de dados de compra e operações de crédito de clientes. 
Os dados, obviamente, eram exemplos descaracterizados para fins acadêmicos.
A visão do produto a ser criado não foi definida pela empresa. A intenção era de, a partir dos dados providos, que montássemos e sugeríssemos produtos válidos 
para sua operação.

O projeto desenvolvimento por minha equipe, a UDA Brasil, possuiu o seguinte objetivo:

Criar uma ferramenta Web de análise da qualidade dos dados, rankeando as fontes de dados de acordo com a consistência, completude e integridade
dos lotes enviados.

### Tecnologias adotadas na solução

#### Flask

Neste projeto os membros de nossa equipe obtiveram o primeiro contato com um framework web, e o utilizado neste momento foi o Flask.

O Flask é um microframework web, que funciona com base na linguagem de programação Python. O radical "micro" em "microframework" é empregado pois o escopo base 
do Flask é enxuto. Ou seja, o Flask não determina ou limita o modo com o qual o seu projeto web será construído. Ele falicita a implamentação básica de um sistema 
web, permitindo diversos modos de desenvolvimento. Por ser leve, enxuto e dinâmico no desenvolvimento de projetos, ele recebe esta denominação.
Saiba mais sobre o Flask em sua [página oficial.](https://flask.palletsprojects.com/en/2.0.x/)

Com o Flask, foram criadas as rotas HTTP que o nosso sistema consumiu. Além disso, em auxílio com a engine de renderização de templates, a
[Jinja2](https://jinja.palletsprojects.com/en/3.0.x/) as páginas de nossa plataforma foram renderizadas para o usuário final.


#### Pandas

O coração do nosso sistema, responsável por facilitar a extração, tratamento e análise dos dados, foi construído com o auxílio da conhecida biblioteca [Pandas](https://pandas.pydata.org/)

O Pandas é uma biblioteca para a linguagem de programação Python, que provê uma série de ferramentas para a extração, conversão e análise de dados. Com o auxílio 
dela, os algoritmos de análise da qualidade dos dados foi construída, o que permitiu que nossa ferramenta pudesse entregar seu principal valor. O ranking das 
fontes por meio da qualidade dos dados enviados por ela.


### Contribuições pessoais

Fui responsável pela programação do script que gerenciava a integração do Arduino com o Servo Motor e o módulo bluetooth.

Por estar focado nesta parte do projeto, pesquisei por diversas plataformas que pudessem construir o protótipo. 
Uma alternativa ao Arduino, a NodeMCU [ver mais](https://nodemcu.readthedocs.io/en/release/), foi estudada e testada para uso. Entretando, como os requisitos do projeto eram atendidos por uma plataforma de uso mais amplo e conhecido como a Arduino, ela foi escolhida para ser utilizada no projeto.

O processo de estudo e implementação do código em testes práticos necessitou de consultas à [documentação oficial do Arduino](https://www.arduino.cc/en/main/docs). Em poucas semanas, a implementação foi finalizada, realizando as etapas explicadas nos capítulos anteriores. 

### Aprendizados Efetivos HS

Neste projeto obtive meu primeiro contato com documentações. Esta experiência me ensinou a buscar informações nas fontes primárias, que são as publicações técnicas geralmente realizadas pelos próprios criadores e responsáveis pelas mais diversas tecnologias. Este aprendizado é de grande valia até hoje em minha trajetória acadêmica e profissional.

Além disso, o desafio de observar um problema prático e ter como tarefa criar uma solução até então inexistente naquele contexto específico, exercitou habilidades que considero importantes para todo analista e desenvolvedor de software. 

Com este desafio, realizei minha primeira decisão de qual tecnologia e tática utilizar em uma solução, e também os detalhes de como implementá-las. Estas decisões são frequentes na carreira de soluções tecnológicas, onde diversas vezes optar pela solução mais eficiente no curto, médio e longo prazo são extremamente necessárias.

Além disso, consegui distinguir a velocidade de profundidade e velocidade em diferentes métodos de pesquisa e estudo. Diversos tutoriais estão disponíveis ensinando a realizar grande partes das etapas de projetos deste tipo, e estes conteúdos possuem sua importância. Entretanto, a consulta na documentação das tecnologias se mostrou muito mais completa, rápida e confiável do que qualquer fonte terceira. Experiência e aprendizado valiosos até hoje. 

No mais, temos os pontos específicos abaixo de aprendizados efetivos:

- Integração Bluetooth entre dispositivos e placa Arduino: Sei fazer com autonomia

- Integração entre placa Arduino e dispositivos periféricos: Sei fazer com autonomia

- Desenvolvimento de scripts em C: Sei fazer com autonomia
