# Projeto 1: 1º Semestre de 2021

### Parceiro Acadêmico

Fatec Prof. Jessen Vidal <br/>

![image](https://user-images.githubusercontent.com/79945984/231303106-6b96699c-af17-4c41-9217-d0792d661b1f.png)

### *Fatec São José dos Campos*

### Visão do Projeto

<p align="justify">
Uma assistente virtual que possua uma ampla gama de funcionalidades é uma tarefa desafiadora que exige conhecimentos técnicos avançados. Nesse contexto, apresentamos o Julius, uma API que consiste em uma assistente virtual especializada em auxiliar o usuário na tomada de decisões relacionadas a investimentos financeiros. Com oito funcionalidades distintas, o Julius se destaca por fornecer informações em tempo real, garantindo ao usuário uma experiência interativa e eficiente.

Entre as funcionalidades oferecidas pelo Julius, destacam-se o código de ações, que permite ao usuário acompanhar o desempenho das ações de empresas listadas em bolsa; a cotação do dia, que apresenta informações atualizadas sobre os valores de moedas e criptomoedas; e o conversor de moedas, que possibilita ao usuário converter valores entre diferentes moedas.

Além disso, o Julius possui outras funcionalidades relevantes, como a possibilidade de consultar a agenda econômica, que apresenta eventos relevantes para o mercado financeiro nacional; a disponibilidade de um chatbot que responde às principais dúvidas dos usuários.
</p>

Para acessar o vídeo de demonstração da aplicação em uso, clique [aqui](https://www.youtube.com/watch?v=oyqu1XqaPPE)

[<img src="https://user-images.githubusercontent.com/79945984/231305890-33255901-7287-40bd-8260-71b93e657ad8.png" widrh="35%" height="10%">](https://www.youtube.com/watch?v=oyqu1XqaPPE "Julius vídeo Demonstração")

### *Demonstração Julius*

Link do repositório do projeto: [https://github.com/TheLooksDatabase/Julius](https://github.com/TheLooksDatabase/Julius)

## Tecnologias utilizadas

### Python [![Python Badge](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)

Python é uma linguagem de programação de alto nível, interpretada e dinâmica, que é amplamente utilizada em áreas como desenvolvimento web, análise de dados, inteligência artificial, automação de tarefas e muitas outras. Uma das principais vantagens do Python é sua sintaxe simples e intuitiva, que facilita a escrita e leitura de código, além de aumentar a produtividade do programador.

Clique [aqui](https://docs.python.org/3/) para acessar a documentação oficial.

### Beautifulsoup4 [![Beautifulsoup4 Badge](https://img.shields.io/badge/BeautifulSoup4-4.9.3-59666C?style=for-the-badge&logo=beautifulsoup&logoColor=white)](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)

O Beautifulsoup4 é uma biblioteca Python utilizada para extrair dados de páginas web de forma fácil e eficiente. Essa biblioteca permite analisar o conteúdo HTML e XML das páginas web e extrair informações específicas, como títulos, parágrafos, links, tabelas e outras tags. 

Clique [aqui](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) para acessar a documentação oficial.

### SpeechRecognition [![SpeechRecognition Badge](https://img.shields.io/badge/SpeechRecognition-3.8.1-blue?style=for-the-badge&logo=python&logoColor=white)](https://pypi.org/project/SpeechRecognition/)

O SpeechRecognition é uma biblioteca Python utilizada para reconhecimento de fala em tempo real ou a partir de arquivos de áudio gravados. Essa biblioteca permite transcrever a fala em texto utilizando diferentes mecanismos de reconhecimento, como o Google Speech Recognition, o Microsoft Bing Voice Recognition, o IBM Speech to Text, entre outros.

Clique [aqui](https://pypi.org/project/SpeechRecognition/) para acessar a documentação oficial.

### Pyttsx3 [![pyttsx3 Badge](https://img.shields.io/badge/pyttsx3-2.90-blue?style=for-the-badge&logo=python&logoColor=white)](https://pypi.org/project/pyttsx3/)

O pyttsx3 é uma biblioteca Python para síntese de voz, que permite a geração de áudio a partir de texto. Essa biblioteca oferece suporte a diferentes mecanismos de síntese de voz, como o eSpeak, o SAPI5 (para Windows) e o NSSpeechSynthesizer (para macOS).

Clique [aqui](https://pypi.org/project/pyttsx3/) para acessar a documentação oficial.

### Google-api-python-client [![Google-api-python-client Badge](https://img.shields.io/badge/Google--api--python--client-v2.25.0-red?style=for-the-badge&logo=google&logoColor=white)](https://developers.google.com/api-client-library/python/start/get_started)

O Google-api-python-client é uma biblioteca Python que oferece acesso às APIs do Google de forma fácil e intuitiva. Essa biblioteca é construída com base no framework de serviços do Google e permite que os desenvolvedores criem aplicativos que interagem com serviços como o Google Drive, Gmail, YouTube, Google Maps, entre outros.

Clique [aqui](https://developers.google.com/api-client-library/python/start/get_started) para acessar a documentação oficial.

### Sqlite3 [![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?&style=for-the-badge&logo=sqlite&logoColor=white)](https://www.sqlite.org/)

O sqlite3 é um módulo da biblioteca padrão do Python que permite acessar e manipular bancos de dados SQLite. O SQLite é um sistema de gerenciamento de banco de dados leve, rápido e simples de usar, ideal para aplicações que não requerem muita escalabilidade ou concorrência. O módulo sqlite3 fornece uma API fácil de usar para criar, modificar e consultar bancos de dados SQLite usando o Python.

Clique [aqui](https://docs.python.org/3/library/sqlite3.html) para acessar a documentação oficial.

## Contribuições pessoais ✔

Durante o desenvolvimento do projeto, tive a responsabilidade de desenvolver o banco de dados local que seria utilizado pela aplicação, utilizando a biblioteca sqlite3 da linguagem Python. A fim de garantir uma estrutura sólida e coerente, me dediquei à elaboração do esquema de banco de dados e à escrita de scripts de criação e manipulação de tabelas, índices e outras estruturas de dados que foram muito relevantes para o projeto.

Além disso, fui responsável pelas funções de conversão de moedas e comparação entre corretoras, utilizando bibliotecas como a currency_converter para a cotação diária das moedas. Aprendi que, apesar de haver diversos tutoriais disponíveis, a consulta à documentação técnica das tecnologias é a melhor forma de obter informações completas, precisas e confiáveis. 

<details><summary>Tabela de Corretoras</summary>

> Aqui temos tabela Corretoras que está armazenando dados de corretoras reais para a nossa aplicação, também sendo responsável por armazenar futuras corretoras que podem ser armazenadas pelo Julius

```kotlin
import sqlite3
con = sqlite3.connect('corretoras.db')
cur = con.cursor()

cur.execute('''CREATE TABLE corretoras
               (cod_corretora int primary key, nome_corretora text, experiencia_investidor text, segurança text, avaliação_final text, custos_mensais_3op real, custos_mensais_5op real, custos_mensais_10op real  )''')


cur.execute("INSERT INTO corretoras VALUES (3 , 'XP INVESTIMENTOS CCTVM S/A' , '5 estrelas' , '5 estrelas' , '91%' , 56.70 , 94.50 , 189.00)")

corretoras = [
(147 , 'ATIVA INVESTIMENTOS S.A. CTCV', '4 estrelas' , '5 estrelas' , '86%' , 45.00 , 75.00 , 150.00),
(386 , 'RICO INVESTIMENTOS', '4 estrelas' , '5 estrelas' , '86%', 26.70, 44.50 , 89.00),
(72 , 'BRADESCO S/A CTVM', '4 estrelas' , '5 estrelas' , '85%' , 44.99 , 62.50 , 250.00),
(735 , 'ICAP DO BRASIL CTVM LTDA', '4 estrelas' , '5 estrelas' , '81%' , 30.00 , 50.00 , 100.00),
(114 , 'ITAU CV S/A', '4 estrelas', '5 estrelas' , '79%' , 48.00 , 125.00 , 400.00),
(90 , 'EASYNVEST – TITULO CV S.A.', '4 estrelas' , '5 estrelas' , '75%' , 30.00 , 50.00 , 100.00),
(262 , 'MIRAE ASSET WEALTH MANAGEMENT', '3 estrelas' , '5 estrelas' , '64%' , 13.75 , 15.73 , 20.68),
(820 , 'BB BANCO DE INVESTIMENTO S/A', '3 estrelas' , ' 5 estrelas' , '60%' , 60.78 , 103.25 , 213.00),
(27 , 'SANTANDER CCVM S/A', '3 estrelas' , '5 estrelas' , '60%' , 45.00 , 112.50 , 350.00)
]
cur.executemany('INSERT into corretoras VALUES (?,?,?,?,?,?,?,?)', corretoras)

for row in cur.execute('SELECT * FROM corretoras'):
 print(row)

con.commit()

con.close()
```
</details>

Também fiquei responsável pela função comparativo entre corretoras, onde utilizei a biblioteca do sqlite3 que usa em conjunto com o arquivo comparativo_corretoras usa o arquivo corretoras.py.

<details><summary>Comparativo entre corretoras</summary>

> Aqui o código da função comparativo entre corretoras que foi desenvolvido em python utilizando a bibiloteca sqlite3 para conectar o código ao banco local corretoras.db

```kotlin
from config import sai_som
import sqlite3
con = sqlite3.connect('corretoras.db')
cur = con.cursor()

def comparativo():
    sai_som('''
        
        Bem-vindo ao comparativo de corretoras!
        
    ''')
    print('''
        Compare duas corretoras em um quesito desejado.
        Atualmente, temos as seguintes corretoras:
        - XP;
        - Itau;
        - Ativa;
        - Rico;
        - Bradesco;
        - Icap;
        - Easynet;
        - Mirae;
        - Banco do brasil;
        - Santander.
        
    ''')

    sai_som('Diga, qual vai ser a primeira corretora: ')
    corretora = input('')


    sai_som('Qual a segunda corretora que deseja fazer uma comparação: ')
    corretora2 = input('')


    sai_som('''
        Atualmente, temos os seguintes critérios de comparação:
    ''')
    print('''
        - Segurança;
        - Experiencia investidor;
        - Avaliação final;
        - Custos mensais 3;
        - Custos mensais 5;
        - Custos mensais 10.
    ''')
    sai_som('Qual o critério de comparação:  ')
    comparativo = input('')


    dict_corretora = {
    'xp': 3,
    'itau': 114,
    'ativa': 147,
    'rico': 386,
    'bradesco': 72,
    'icap': 735,
    'easynet': 90,
    'mirae': 262,
    'banco do brasil': 820,
    'santander': 27
    }

    dict_fator_comparativo = {
        'segurança': 'segurança',
        'experiencia investidor': 'experiencia_investidor',
        'avaliação final': 'avaliação_final',
        'custos mensais 3': 'custos_mensais_3op',
        'custos mensais 5': 'custos_mensais_5op',
        'custos mensais 10': 'custos_mensais_10op'
    }

    custos_mensais= []

    query_parameters = (dict_corretora[corretora.lower()], dict_corretora[corretora2.lower()])

    for row in cur.execute(f'SELECT {dict_fator_comparativo[comparativo.lower()]} FROM corretoras WHERE cod_corretora == ? or cod_corretora == ?', query_parameters):
        custos_mensais.append(row[0])

    sai_som(f'Os dados da corretora {corretora} são de: {custos_mensais[0]} e da corretora {corretora2} são de: {custos_mensais[1]} ')

    con.commit()
    con.close()
```
</details>

Também fui responsável pela funcionalidade de Conversor de moedas, que utiliza a API currencyConverter e que é responsável pela cotação atualizada em tempo real das moedas de distintas nacionalidades e com isso realizar a conversão de moeda para moeda durante o uso da aplicação

<details><summary>Conversor de Moedas</summary>

> Aqui, o código da função conversor de moedas desenvolvido em python que está utilizando a api currencyConverter que é responsável por retornar a cotação atual de determinada moeda escolhida pelo usuário

```kotlin
from currency_converter import CurrencyConverter
from config import sai_som

def Conversor_Moedas():

    c = CurrencyConverter()

    sai_som('''
        Para realizar a conversão, use os seguintes códigos:
    ''')
    print('''
        'EUR' - para Euros;
        'CAD' - para dólar Canadense;
        'USD' - para dólar americano;
        'BRL' - para real brasileiro;
        'GBP' - para libra;
    ''')

    sai_som('Qual é a moeda do seu valor? ')
    actually = str(input('')).upper()
    
    sai_som('Qual é o seu valor? ')
    valor = float(input(''))
    
    sai_som('Qual é a sua moeda final? ')
    final = str(input('')).upper()
    
    convert = c.convert(valor, actually, final)

    sai_som(f'{valor} {actually} são {convert:.2f} {final}. ')
```
</details>

## Aprendizados Efetivos ![Aprendizados efetivos](https://img.shields.io/badge/Aprendizados%20efetivos-100%25-brightgreen?style=for-the-badge)

Durante o desenvolvimento desse projeto, fui exposto pela primeira vez à importância de se consultar documentações técnicas primárias para obter informações precisas e confiáveis sobre as tecnologias utilizadas. Essa experiência foi fundamental para o meu desenvolvimento profissional e acadêmico, pois aprendi a buscar informações detalhadas diretamente de documentações oficiais das tecnologias.

Devido à novidade que foi essa experiência que o API pode me proporcionar, grande parte do meu tempo foi dedicado ao estudo de conceitos e técnicas relevantes para a implementação do banco de dados e outras funcionalidades da aplicação. Esse estudo foi essencial não só para a criação de uma base sólida para a gestão de dados locais, que atendeu perfeitamente aos requisitos do projeto mas também para meu desenvolvimento pessoal.

- Criação de um banco de dados local utilziando bibiliotecas especificas: sei fazer com autonomia
- Gerenciamento e utilização de uma nova gama de APIs e bibliotecas disponiveis para o desenvolvimento do projeto: sei fazer com autonomia

## Navegação Entre Projetos :link:
 
<p align="justify" style="font-family:roboto;"><li>1º Semestre: Julius - Assistente virtual criado para facilitar a sua vida financeira.</li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/SGBD_Health.md"> 2º Semestre: SGBD Health - Aplicação de monitoramento voltada para SGBD, focada em performance e desempenho</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Descont0n.md"> 3° Semestre: Descont0n - Ferramenta para criação de promoções e regras de negócio com foco em E-commerce</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/MCS.md"> 4° Semestre: MCS - Sistema ERP que visa gerenciar e controlar dados fornecidos pelos clientes</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/TechNinjas.md"> 5° Semestre: TECH NINJAS - Sistema de automatização fluxo de controle dos arquivos armazenados em cloud</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/README.md"> Voltar para página inicial</a></li></p>