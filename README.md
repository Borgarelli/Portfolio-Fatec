# Portfólio Fatec

# Kauã Walbon Santos Borgarelli Tavares

## Introdução

Olá, seja bem-vindo. Sou o Kauã Borgarelli, estudante de Banco de Dados pela FATEC Prof. Jessen Vidal.

Tenho 19 anos e estou em busca de um estágio. <br/>

![https://user-images.githubusercontent.com/79945984/193151179-79c30859-fbd7-42ce-9c7a-d9933e622429.jpg](https://user-images.githubusercontent.com/79945984/193151179-79c30859-fbd7-42ce-9c7a-d9933e622429.jpg)

### *Figura 00. Eu*

### Meus principais conhecimentos

### SQL

Minha atuação mais presente durante a Fatec é com os desenvolvimentos das modelagens relacionais, Lógicos e modelos físicos dos bancos nos API, é com a parte que eu sinto que mais contribuo em quesitos de conhecimento.

### HTML-5 e CSS-3

Html e CSS é o que eu mais estou focado em estudar atualmente, sinto que com o passar dos semestres, consigo contribuir cada vez mais no front-end dos projetos.

### Projetos Integradores durante a graduação

Durante a minha gradução, trabalhei no desenvolvimento de trabalhos chamados de "Projetos integradores". Um projeto integrador tem o objetivo de solucionar um problema do mundo real, utilizando os conhecimentos adquiridos durante o decorrer dos semestres.<br/>
Abaixo todos estes projetos serão descritos, detalhando o problema, solução proposta (e entregue), e os aprendizados extraídos de cada um deles.

# Projeto 1: 1º Semestre de 2021

### Parceiro Acadêmico

Fatec Prof. Jessen Vidal (proposta realizada pelo docente responsável pela disciplina que ordenou o projeto)

### Visão do Projeto

Desenvolver um sistema de Vending Machine, criando a tela de interface com o cliente, onde seria realizada a seleção e compra de produtos. Após este processo, o aplicativo desenvolvido deveria enviar um sinal ao hardware da máquina de vendas, que liberaria o acesso ao produto adquirido. Fora destes momentos, o acesso aos produtos deveria permanecer restrito, trancado pelos dispositivos.

### Tecnologias adotadas na solução

### Interface com o usuário - App Inventor

A interface com o cliente foi realizada através de uma tela de smartphone, que simulava o display da vending machine. Um aplicativo desenvolvido através da ferramenta App Inventor, para o sistema operacional Android, provia ao usuário final as telas de seleção de produtos e finalização de compra.

A programação nesta plataforma se dá em blocos. Diversos recursos de linguagens de programação tradicionais (condições, loops e operações) em blocos ilustrativos, que tornam a construção de rotinas e lógicas visuais e, desta forma, mais intuitivas.

Por conta desta natureza da ferramenta - [App Inventor](https://appinventor.mit.edu/) - não há código fonte a ser disponibilizado.

### Arduino

O funcionamento da vending machine foi construído utilizando o Arduino, com a placa central e dois periféricos. Um servo motor e um módulo Bluetooth HC-05.

O Arduino é uma plataforma de prototipagem. Usualmente, ao falar em "Arduino", nos remetemos a placa central que liga diversos dispositivos que são interligados por ela.

Entretanto, o Arduino como plataforma vai um pouco além, pois também fornece diversos recursos - comunicação Serial, alimentação elétrica, periféricos da própria plataforma, etc - que facilitam a prototipagem de sistemas embarcados, e que podem servir às mais diversas finalidades específicas.

Estes recursos facilitam a construção de protótipos das mais diversas finalidades. A programação simples e direta de periféricos como motores, luzes e sensores, tornam quase que ilimitadas as possibilidades de protótipos que podem ser construídas utilizando o Arduino.

O Servo Motor ou o módulo HC-05, dentre outros, fazem parte desta plataforma e foram utilizados neste projeto. Estes dispositivos em conjunto possibilitam a prototipagem de sistemas embarcados. E, neste exemplo, de um que seria responsável apenas por receber instruções para abrir e trancar uma porta.

### Módulo Bluetooth HC-05

A conexão entre o app Android criado e o sistema da máquina de vendas foi realizada via Bluetooth. Para isso, utilizamos o módulo Bluetooth HC-05.

O módulo HC-05 é um dispositivo serial de comunicação Bluetooth. [ver mais](https://www.gme.cz/data/attachments/dsh.772-148.1.pdf)

Este módulo possui 4 pinos principais de conexão com a placa Arduino. Dois pinos são responsáveis pela comunicação serial (RXD e TXD), e dois pinos de alimentação (VCC) e o que fecha o curto para garantir a corrente elétrica, o GND.

Na prática, a conexão destes pinos fica da seguinte forma:

![https://user-images.githubusercontent.com/45850297/132968177-13fa8c56-ff56-4bd2-9ccc-b75e205529e5.png](https://user-images.githubusercontent.com/45850297/132968177-13fa8c56-ff56-4bd2-9ccc-b75e205529e5.png)

### *Figura 01. Ilustração dos conectores Arduino*

O módulo possui versões 5V e 3.3V. Como a alimentação padrão mais próxima no Arduino é de 5V, caso o módulo seja de 3.3V, é necessário utilizar resistências para evitar danos elétricos ao módulo. No caso atual, este preparo não foi necessário, pois utilizamos uma versão 5V.

Os dispositivos internos da máquina eram compostos de uma placa Arduino e um Servo Motor. Este último era responsável por abrir a porta que liberava acesso ao produto selecionado e trancá-lo novamente após isso.

### Servo Motor

O servo motor é um periférico que pode ser utilizado no Arduino. Ele possibilita a geração de movimentos rotacionais controlados.
Por exemplo: com um servo motor, podemos realizar rotações limitadas, porém com maior precisão. Suas versões mais comuns não permitem uma rotação contínua, como uma roda de carro, por exemplo.

Entretanto, caso seja necessário realizar rotações específicas, determinando até mesmo a quantidade de graus que o movimento deve ter, o servo motor é o ideal para esta demanda. Como necessitávamos de uma tranca automática, ele atendeu à necessidade do projeto.

A montagem deste dispositivo é similar a do módulo HC-05. Temos uma demonstração de como ela ficaria na prática:

![https://user-images.githubusercontent.com/45850297/132969607-4f0f0591-94f9-4d43-9529-ef4265b4aa02.png](https://user-images.githubusercontent.com/45850297/132969607-4f0f0591-94f9-4d43-9529-ef4265b4aa02.png)

### *Figura 02. Esquema de conexão dos periféricos à placa Arduino*

Como pode ser visto, a alimentação ainda é realizada conectando as saídas de 5V e GND, que fecham o circuito de alimentação, e um pino é escolhido para recebimento das instruções de rotação. Neste exemplo, o de número 6.

### Contribuições pessoais

Fui responsável pela programação do script que gerenciava a integração do Arduino com o Servo Motor e o módulo bluetooth.

Por estar focado nesta parte do projeto, pesquisei por diversas plataformas que pudessem construir o protótipo.
Uma alternativa ao Arduino, a NodeMCU [ver mais](https://nodemcu.readthedocs.io/en/release/), foi estudada e testada para uso. Entretanto, como os requisitos do projeto eram atendidos por uma plataforma de uso mais amplo e conhecido como a Arduino, ela foi escolhida para ser utilizada no projeto.

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

# Projeto 2: 2º semestre de 2021

### Parceiro Acadêmico

Necto Systems <br/>

![https://user-images.githubusercontent.com/74321890/200952858-ff867019-d4c6-49cf-9c2a-9508546a5ed9.png](https://user-images.githubusercontent.com/74321890/200952858-ff867019-d4c6-49cf-9c2a-9508546a5ed9.png)

### *Figura 01. Necto Systems*

[<img src="https://user-images.githubusercontent.com/79945984/225161808-9c6c5ffa-ff60-48cb-8bce-95d81551aeb7.png" width="35%" height="10%">](https://youtu.be/NhDe9-Z_dvk "DescontOn vídeo Demonstração")

### *Figura 02. Demonstração SGBD Health*

Link do repositório do projeto: [https://github.com/DolphinDatabase/SGBD_Health](https://github.com/DolphinDatabase/SGBD_Health)

### Tecnologias utilizadas

## PostgreSQL

PostgreSQL é um sistema gerenciador de banco de dados objeto-relacional baseado no POSTGRES, Versão 4.2, desenvolvido na Universidade da Califórnia no Departamento de Ciências da Computação em Berkeley, o qual foi pioneiro em muitos conceitos que vieram a estar disponíveis em alguns bancos de dados comerciais mais tarde. O PostgreSQL é um banco de dados objeto-relacional (sem relação com linguagens de programação orientadas a objetos), em que cada coisa criada é tratada como um objeto, tais como bancos de dados, tabelas, views, triggers, etc.

Para mais informações [clique aqui](https://www.postgresql.org/about/).

## SQlite

SQLite é um sistema de gerenciamento de banco de dados relacional leve, embutido e amplamente utilizado em aplicativos móveis, navegadores da web e outros softwares que precisam armazenar dados localmente. Ele é uma biblioteca escrita em C que oferece recursos avançados de gerenciamento de banco de dados, como transações ACID, integridade referencial e indexação avançada, tornando-o uma escolha popular para desenvolvedores que precisam de uma solução de banco de dados confiável e fácil de usar

Para mais informações [clique aqui](https://www.sqlite.org/about.html).

## Java

<p align="justify">
Java é uma linguagem de programação de alto nível, orientada a objetos e multiplataforma lançada em 1995 pela Sun Microsystems (agora Oracle). Ela é amplamente usada para desenvolver aplicativos, jogos, sistemas de gerenciamento de banco de dados, aplicativos da web e muito mais. Java é portátil, seguro, escalável e capaz de lidar com aplicativos complexos, com suporte de uma grande comunidade de desenvolvedores em todo o mundo.

Para mais informações [clique aqui](https://www.java.com/pt-BR/download/help/whatis_java.html).

### Contribuições pessoais

Minha função principal no projeto foi liderar a modelagem do banco de dados no PostgreSQL e avaliar a utilização do SQLite para armazenar arquivos CSV. Trabalhei em estreita colaboração com a equipe de desenvolvimento para garantir a integração adequada do banco de dados com a aplicação e o sucesso do projeto.

### Aprendizados Efetivos

Este projeto marcou o início de uma verdadeira API com clientes parceiros da Fatec, proporcionando experiências incríveis e desafiadoras ao longo do semestre. O principal foco foi o desenvolvimento do banco de dados para atender a todos os requisitos necessários para a aplicação, permitindo o armazenamento de todos os dados necessários para os testes e entrega final do projeto. 

O projeto teve um papel fundamental na preparação dos alunos para a indústria e no desenvolvimento de habilidades importantes na área de tecnologia da informação.

- Trabalhar com SGBD: sei fazer com autonomia.
- Criar tabelas, relacionamentos e modelagem: sei fazer com autonomia.
- Desenvolvimento de scripts em Java: sei fazer com auxilio.

### *Figura 05. MidAllº*

https://user-images.githubusercontent.com/79945984/225164162-7dbdd56f-5db6-4819-8749-0c6934d5eeb2.png


### Visão do Projeto
https://user-images.githubusercontent.com/79945984/225164049-635e76ed-7868-46a3-a2b1-79f6935fad11.png

Ferramenta para criar promoções de E-commerce, onde as mecânicas de promoções são feitas de forma flexível e de rápida atualização no sistema. As regras de promoções são cadastradas e posteriormente aplicadas no momento em que os itens são adicionados ao carrinho.

Atualmente implementamos e apresentamos o cadastro dos produtos dentro de promoções registradas dentro do servidor/banco de dados, utilizando operadores lógicos para criar diferentes mecânicas de promoções, os descontos são aplicados dentro da sacola de compras e possui uma visualização dedicada para conferência e escolha de promoções.

Além disso, há a autonomia fornecida ao usuário para editar, remover, arquivar ou desarquivar seus produtos e também para editar, deletar, interromper ou ativar promoções de uma visualização de maneira prática e intuitiva dos produtos e promoções cadastradas através da listagem que possui um filtro para que seja possível diferenciar quais os status de produtos e promoções.

Para acessar o vídeo de demonstração da aplicação em uso, clique [aqui](https://youtu.be/NhDe9-Z_dvk):

[<img src="https://github.com/DolphinDatabase/DescontOn/blob/47f0f23ee3d7710b472fc1ff26d06da50237681e/Imagens/imagem_2022-04-15_155641874.png" width="40%">](https://youtu.be/NhDe9-Z_dvk "DescontOn vídeo Demonstração")

### *Figura 04. Aplicação em ação - Motor de regras integrado a um E-commerce, realizando todo o processo de cadastro de novos produtos e o processo de criação de novas regras de desconto e aplicar a seus produtos*

Link do repositório do projeto: [Clique aqui](https://github.com/DolphinDatabase/DescontOn)

### Tecnologias utilizadas para a aplicação

### JQuery <a href="https://jquery.com" target="_blank"><img width="65" height="20" src="https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white"/></a>

jQuery é uma biblioteca JavaScript criada por John Resig em 2006. É como um software de código aberto: seu uso é licenciado pela Massachusetts Institute of Technology (MIT) e pelo GNU General Public License (GPL). Sua principal finalidade é associar-se aos elementos JavaScript em HTML para conferir mais dinamismo e usabilidade às páginas na internet.

Suas linhas de código simplificam os scripts interpretados pelo navegador do client-side e por esse motivo é uma das bibliotecas mais populares na comunidade de desenvolvedores. Clique [aqui](https://jquery.com/) para acessar a documentação oficial.

<details> <summary>Exemplo de códgio em Jquery</summary>

```kotlin
 $(document).ready(function(){
	// Ações aqui
});

Veja que neste código, ele executa o código quando o document estiver "ready", ou seja, "pronto".
$(document).ready(function(){
	alert("Documento Iniciado");
});


Read more: http://www.linhadecodigo.com.br/artigo/2210/iniciando-em-jquery.aspx#ixzz7mAVxiUF0
```
</details>

### Thymeleaf <a href="https://www.thymeleaf.org" target="_blank">![Thymeleaf](https://img.shields.io/badge/Thymeleaf-darkgreen?style=flat-square&logo=thymeleaf)</a>

O Thymeleaf é uma template engine voltado para projetos Java que facilitam a criação
de páginas HTML. Permitindo a troca de informações entre o código Java e as páginas
HTML, de tal maneira garantindo que o desenvolvedor consiga criar templates de
forma mais simples e de uma maneira mais agilizada para suas aplicações.

Ele permite modelagem natural, pode fazer processamento complexo e nos
permite definir facilmente dialetos personalizados. Além disso, o Thymeleaf
facilita a colaboração de desenvolvedores front-end e back-end no mesmo
arquivo de modelo, gerando um grande aumento de produtividade. Clique [aqui](https://www.thymeleaf.org/) para acessar a documentação oficial.

<details> <summary>Exemplo de códgio em Thymeleaf</summary>

```kotlin
 @Controller
public class HomeController {

    @GetMapping("/")
    public String home(ModelMap model) {
        model.addAttribute("nomeDoAtributo", "Treinaweb");

        return "home";
    }
}
```
</details>

### Spring Boot <a href="https://spring.io/projects/spring-boot" target="_blank"><img src="https://img.shields.io/badge/Spring-6DB33F?style=flat-square&logo=spring&logoColor=white"/></a>

O Spring Boot é um framework Java open source que tem como objetivo
facilitar esse processo em aplicações Java. Trazendo mais agilidade para o processo
de desenvolvimento com uma infinidade de ferramentas surge todos os dias visando
justamente acelerar o processo de criação e implantação de soluções nos mais
variados ambientes.
O Spring torna a programação Java mais rápida, fácil e segura para todos. O
foco do Spring em velocidade, simplicidade e produtividade o tornou o
framework Java mais popular do mundo. Clique [aqui](https://spring.io/projects/spring-boot) para acessar a documentação oficial.

<details> <summary>Exemplo de códgio em Springboot</summary>

```kotlin
@RequestMapping("v1/books")
public class BookRestService {
 
    private final BookService bookService;
 
    @ResponseStatus(HttpStatus.OK)
    @RequestMapping(value = "/{id}", method = RequestMethod.GET)
    public BookResource getById(@PathVariable Integer id) {
        throw new NotImplementedException();
    }
 
    @ResponseStatus(HttpStatus.CREATED)
    @RequestMapping(method = RequestMethod.POST)
    public BookResource save(@RequestBody BookResource bookResource) {
        throw new NotImplementedException();
    }
 
}
```
</details>

### Bootstrap <a href="https://getbootstrap.com" target="_blank"><img src="https://img.shields.io/badge/Bootstrap-563D7C?style=flat-square&logo=bootstrap&logoColor=white"/></a><br/>

O Bootstrap é um framework front-end que veio para facilitar e agilizar o
trabalho, oferecendo padrões para HTML, JavaScript e CSS de acordo com o site
CiaWebsites. Foi desenvolvido por Jacob Thorton e Mark Otto com o objetivo de
facilitar a programação de um site web e otimizar tempo.

Este fornece uma grande variedade de plugins e é compatível com qualquer linguagem de programação, o que facilita para os desenvolvedores de site. É aplicado na criação de sites responsivos (mobile).
Bootstrap tem uma abordagem mobile first, uma estratégia que otimiza o
código para dispositivos móveis primeiro e, então, é que se começa a pensar
em media queries para aparelhos maiores. Clique [aqui](https://getbootstrap.com/) para acessar a documentação oficial.


<details> <summary>Exemplo de códgio em Bootstrap</summary>

```kotlin
<pre><code>&lt;p&gt;Exemplo de texto aqui...&lt;/p&gt;
&lt;p&gt;Outro exemplo de texto aqui...&lt;/p&gt;
</code></pre>
```
</details>

### Maven

O Apache Maven é uma ferramenta que oferece automação e gerenciamento
de projetos Java (mas podem ser utilizada com outras linguagens), padronizando a
construção e publicação de suas aplicações.

Por ser extremamente flexível agrega agilidade e qualidade ao produto, além de permitir que sejam adicionados plugins a si e estender suas funcionalidades. Normalmente, até algum tempo atrás, cada projeto tinha sua própria estrutura, seu próprio jeito de gerar pacotes, de efetuar cada um
destes passos. Projetos complexos, com vários módulos, ainda podem precisar que
estes sejam compilados em determinada ordem, para que o pacote final seja criado.

O Apache Maven é uma excelente ferramenta de apoio a qualquer equipe
que trabalhe com projetos Java (outras tecnologias também são suportadas),
fornecendo aos desenvolvedores uma forma de automatizar e padronizar a
construção e publicação de suas aplicações. Clique [aqui](https://maven.apache.org/) para acessar a documentação original.

<details> <summary>Exemplo de códgio em Maven</summary>

```kotlin
public class App {
    public static void main(String[] args) {
        System.out.println("Hello World!"); 
    }  
}

public class AppTest extends TestCase {
    
    public AppTest(String testName) {
        super(testName);  
    }
  
    public static Test suite() {
        return new TestSuite(AppTest.class);  
    }
  
    public void testApp() {
        assertTrue(true);  
    }  
  
}
```
</details>

### Contribuições pessoais

Fui responsável pela criação do banco de dados utilizado para toda a aplicação. Para isso, foi necessário estudar sobre a utilização de um SGBD que eu não tinha experiência nenhuma, que era o Oracle Database, que utiliza uma sintaxe totalmente diferente de outros SGBD mais comuns, como MySql e Postgres.

Durante a preparação para iniciar o desenvolvimento do projeto, consultei diversos materiais e documentações sobre como era o ambiente Oracle como requisitos para a utilização do mesmo, como configura-lo, como manuseá-lo e etc. Além disso fui responsável pela modelagem completa do nosso banco, gerado através do Brmodelo 3.0

BrModelo é uma ferramenta desktop voltada para o desenvolvimento de projeto de banco de dados relacionais, incluindo as etapas conceitual, lógico e físico, com uma ampla utilização em toda a área de computação em todo o Brasil. E nele é que geramos os três tipos de modelagem.

### Modelo Conceitual


A maior dificuldade para o aprendizado das técnicas de modelagem em banco de
dados é entender uma situação de um problema real e converte-lo, criando assim uma solução.
O profissional da área de informática precisa entender o problema e conceituar em como será feita a solução e, para isso, duas coisas podem ser consideradas imprescindíveis:
a) Saber ouvir o cliente/usuário abstraindo da conversa o que é realmente útil para
implementar a solução;
b) Conhecer as técnicas de modelagem a fim de representar o problema de forma
conceitual antes de iniciar a implementação.

<details><summary>Conceitual</summary>
<img width="250" src = "https://user-images.githubusercontent.com/79945984/194174800-ae3951d9-a8af-4029-bd9d-7f703e59b7ad.png"/>
<p>Exemplo de uma modelagem Conceitual, onde a tabela Vendas se conecta com as outras tabelas </p></details>

### Modelo Lógico

O modelo lógico é o resultado ou produto da conversão de um modelo conceitual
para um determinado tipo de banco de dados, ou segundo o professor Carlos Alberto Heuser, “Um modelo lógico é uma
descrição de um banco de dados no nível de abstração visto pelo usuário do sistema gerenciador de banco de dados”.
Por isso, nesta fase do processo de modelagem de dados, o responsável pelo projeto já deve ter
conhecimento do tipo de banco de dados no qual o projeto será implementado (relacional,
hierárquico, objeto - relacional, entre outros).

<details><summary>Lógico</summary>
<img width="250" src = "https://user-images.githubusercontent.com/79945984/194174919-d99831d1-0036-489c-90a6-f3b4b8422532.png"/>
<p>Exemplo de uma modelagem Lógica, onde a tabela Vendas recebe as chaves das outras tabelas </p></details>

### Modelo Físico

É o modelo que descreve a forma como os dados serão armazenados no SGBD, nesta
fase, o modelo lógico é convertido, no caso dos bancos relacionais em linguagem DDL (data
description language) e as regras descritas no modelo conceitual são convertidas em regras de
integridade.
Dentre os tipos de bancos de dados, os mais comuns são os relacionais, embora esteja cada vez mais
crescente a quantidade dos bancos de dados orientados a objetos.
Neste contexto, o escopo limita-se a influência em cima dos bancos relacionais e a
forma de modelá-los.

<details><summary>Físico</summary>
<img  width="250" src = "https://user-images.githubusercontent.com/79945984/194175053-cbb6e065-4c3b-46ad-adf2-4c142f851c26.png"/>
<p>Exemplo de uma modelagem fisica, onde é possivel de maneira com mais detalhes através de código, como é feita a conexão entre as tabelas e como elas passam suas chaves primárias para tabela Vendas</p></details>

Após uma profunda pesquisa sobre todos estes tópicos, fui responsável por modelar todos os dados que armazenamos e seriam cadastrados pelos clientes/usuários através da nossa aplicação.

### Aprendizados Efetivos HS

No desenvolvimento das modelagens do nosso E-commerce, aprendi mais sobre a estruturação de um mesmo. Foi a primeira vez em que trabalhei de fato com uma aplicação front-end voltada principal para web.
Por conta desta experiência, fui inserido a um novo nível de exigência para a construção de um sistema web, tendo que me preocupar com o formato e conteúdo específico das requisições de entrada possiveis no serviço desenvolvido.

Além disso, aprendi muito sobre uma área não diretamente relacionada a tecnologias de construção de software, mas que eram essenciais para cumprir com as regras informadas pelo cliente, sejam elas em vendas, aplicações de descontos e regras de negócio, é algo que nunca pensei em trabalhar em conjunto antes. Esta habilidade de aprender de forma ágil sobre temas que sequer pensei em trabalhar, por conta das infinitas possíveis áreas de atuação de possíveis futuros clientes, foi de um valor excepcional para mim e para minha formação como aluno da Fatec.

- Criação de banco de dados para armazenamento de produtos cadastrados e novas regras geradas pelo usuário/cliente: sei fazer com autonomia
- Modelagem completa para armazenar todos os dados oferecidos e requisitados pelo usuário e pela aplicação: sei fazer com autonomia
<br/>

# Projeto 4 - 1º semestre de 2021

## Empresa parceira:

IACIT

<img src="[https://user-images.githubusercontent.com/54003876/142727570-6c418f49-5e00-437c-9d9e-5b27131974bb.png](https://user-images.githubusercontent.com/54003876/142727570-6c418f49-5e00-437c-9d9e-5b27131974bb.png)" height="300"/>

### *Figura 06. IACIT (Fonte: [https://www.iacit.com.br/](https://www.iacit.com.br/))*

Um importante polo da indústria aeroespacial brasileira, fundada em 1986, a IACIT é uma empresa brasileira com sede em São José dos Campos - SP. Com capacitação no desenvolvimento de produtos e sistemas aplicados  para o segmento de navegação aérea, com certificação como Empresa Estratégica de Defesa (EED).

### Visão do Projeto

Desenvolver uma ferramenta capaz de criar, organizar e gerenciar atas de reunião. Com requisitos específicos do cenário da empresa parceira, como a necessidade de gerenciar logs de atualização e criação, exportação das atas em documentos de diferentes formatos, e usabilidade mobile.

O [Typext](https://github.com/Typext) foi desenvolvido para atender a demanda. Este sistema permite a criação, gerenciamento, análise para aprovação/reprovação de atas digitais. Além de funcionalidades extras como exportação do documento em PDF, disponibilização de atas para pessoas não necessariamente cadastradas na ferramentas e diversas outras features.

<img src="[https://user-images.githubusercontent.com/54003876/142728582-46164603-7014-4451-a431-804153a612bf.png](https://user-images.githubusercontent.com/54003876/142728582-46164603-7014-4451-a431-804153a612bf.png)" height="500"/>

### *Figura 07. Typext (Fonte: [https://github.com/Typext](https://github.com/Typext))*

## Tecnologias utilizadas:

![https://user-images.githubusercontent.com/54003876/142728799-f87fdad3-06a5-4ff3-9518-5c1f80624bd1.png](https://user-images.githubusercontent.com/54003876/142728799-f87fdad3-06a5-4ff3-9518-5c1f80624bd1.png)

### *Figura 08. Tecnologias Typext (Fonte: [https://github.com/Typext](https://github.com/Typext))*

Assim como no projeto anterior, a aplicação front-end foi construída com a biblioteca React.Js.
Porém, neste projeto houve uma mudança da stack dos serviços e API do back-end. Apenas Node.Js foi utilizado em sua construção, com a linguagem Typescript.
Assim foram programadas todas as rotas HTTP, conexão com o banco de dados e manutenção do banco para alterações, por meio de migrations.
A base de dados utilizada foi mantida, utilizando o PostgreSQL.

### Contribuições pessoais

Desenvolvimento de features e estruturas do backend da ferramenta. O sistema foi construído em TypeScript, com Node.js. No desenvolvimento deste projeto, diversos desafios foram enfrentados e realizados pelo time do backend. Alguns deles citados abaixo:

- Registro de logs personalizados de ações dos usuários;
- Atualização de registros complexos como a ata;
- Disponibilização de documentos em diferentes formatos a partir de entidades na nossa ferramenta;
- Inclusão de tecnologias de empresas parceiras como o calendário, que permitia agendamento de reuniões.

Atuei em todas estas frentes, criando diferentes rotas e serviços para a implementação de várias features do sistema. Minhas principais contruibuições foram a criação e recuperação de logs e atualização dos registros de usuários e atas.

## Aprendizados Efetivos HS

- Desenvolvimento de serviços CRUD: Sei fazer com autonomia; <br/>
- Desenvolvimento utilizando Typescript: Sei fazer com autonomia; <br/>
- Utilização de ORM's com banco relacional: Sei fazer com autonomia; <br/>

# Projeto 5 - 2º semestre de 2021

## Empresa parceira:

GSW

<img src="[https://user-images.githubusercontent.com/54003876/142731143-f3afb070-80b4-442d-ba68-ddd77247dc5b.png](https://user-images.githubusercontent.com/54003876/142731143-f3afb070-80b4-442d-ba68-ddd77247dc5b.png)" height="150"/>

### *Figura 09. GSW (Fonte: [https://www.gsw.com.br/](https://www.gsw.com.br/))*

A GSW é uma empresa brasileira. No mercado desde 1991, sua atuação é focada em produzir soluções para gerenciamento e controle de processos e negócios.

### Visão do Projeto

A empresa apresentou a necessidade de uma extensão de um produto já existente, que consiste em um portal de anúncio e vendas de imóveis.<br/>
Tal extensão deveria consistir em um marketplace para anúncio e vendas de automóveis, que permitisse que comprador e vendedor se encontrem, conversem e negociem os processos de compra e venda.

Além disso, a ferramenta deveria possibilitar a carga de alguns dados, como de novos usuários e anúncios.

Como solução ao problema, foi criada a plataforma [OneCar](https://github.com/OneCar-API). A OneCar é uma aplicação Web e mobile para anúncio de veículos à venda.
A OneCar possui diversas funcionalidades, como:

- Cadastro de usuários e anúncios automatizados por meio de cargas;
- App mobile para visualização e busca de anúncios;
- Comunicação em tempo real com o vendedor, assim como acesso ao seu contato em casos onde isso é desejado pelas partes;
- Busca pelos anúncios por palavras-chaves e itens dos veículos.

<img src="[https://user-images.githubusercontent.com/54003876/142731498-cf7ccb60-cc0a-4bce-a24e-a82d8b916d17.png](https://user-images.githubusercontent.com/54003876/142731498-cf7ccb60-cc0a-4bce-a24e-a82d8b916d17.png)" height="500"/>

### *Figura 10. OneCar*

## Tecnologias utilizadas:

- NodeJS <br/>
- Typescript <br/>
- Express <br/>
- PostgreSQL <br/>
- ReactJS <br/>
- Docker <br/>

Mantendo a linha dos dois projetos anteriores, utilizamos React para o front-end, inclusive com o Reactive Native para as telas mobile.
No backend, as mesmas linguagens e ferramentas foram usadas em relação ao projeto anterior.

### Contribuições pessoais

Desenvolvimento do backend da aplicação, em especial serviços CRUD e o chat da ferramenta. <br/>
Fui responsável pelo desenvolvimento da feature de comunicação em tempo real entre comprador e vendedor foi desenvolvida utilizando web socket, com a biblioteca [Socket.Io](https://socket.io/). A inclusão desta tecnologia foi de grande desafio e valia no projeto, pois é a primeira vez que utilizamos este tipo de comunicação entre cliente e servidor em um projeto integrador, então foi necessário um aprendizado ágil para sua implementação.<br/>

## Aprendizados Efetivos HS

- Desenvolvimento de serviços CRUD: Sei fazer com autonomia;
- Desenvolvimento utilizando Typescript: Sei fazer com autonomia;
- Utilização de ORM's com banco relacional: Sei fazer com autonomia;
- Utilização de banco NoSQL: Sei fazer com autonomia;
- Comunicação em tempo real entre cliente e servidor com web socket: Sei fazer com autonomia.

# Projeto 6 - 1º semestre de 2022

## Empresa parceira:

UOL

<img src="[https://conteudo.imguol.com.br/c/home/layout/vueland/icons/brand/uol-logo-full.svg?v4](https://conteudo.imguol.com.br/c/home/layout/vueland/icons/brand/uol-logo-full.svg?v4)" height="150"/>

### *Figura 11. UOL (Fonte: [https://www.uol.com.br/](https://www.uol.com.br/))*

A UOL é uma companhia brasileira, fundada em 1996. Pioneira no mercado online nacional, foi a dona do primeiro portal de conteúdos no país. O portal de UOL, que carrega o nome da empresa, segue sendo o maior do Brasil.

### Visão do Projeto

Nosso parceiro deste projeto solicitou a criação de uma ferramenta que pudesse prever a indisponibilidade de seus serviços online. O produto desenvolvido deveria ser capaz de monitorar a saúde da aplicação e prever que num futuro breve um problema pode ocorrer, caso o cenário seja este.

Considerando a larga escala de utilização dos produtos do nosso parceiro, prever possíveis indisponibilidades futuras seria um ótimo mecanismo de garantir disponibilidade máxima para seus usuários.

Para atender às demandas solicitas, a [Orbit](https://github.com/orbit-api) foi desenvolvida. A Orbit é uma ferramenta de monitoramento que tem como objetivo coletar os dados de saúde de um serviço e, com base nos dados coletados de cenários de indisponibilidade, pode prever um novo cenário de queda do serviço monitorado. Caso um evento deste tipo seja previsto, os responsáveis pela aplicação são notificados de que um possível problema deverá ocorrer.

<img src="[https://user-images.githubusercontent.com/56441318/160112708-193a18fe-2241-427c-8fe0-2dc23324b48a.png](https://user-images.githubusercontent.com/56441318/160112708-193a18fe-2241-427c-8fe0-2dc23324b48a.png)" height="500"/>

### *Figura 12. Orbit*

## Tecnologias utilizadas:

- Java <br/>
- Spring Boot <br/>
- Hibernate <br/>
- PostgreSQL <br/>
- Vue Js <br/>
- Docker <br/>
- [Locust.io](http://locust.io/) <br/>
- Prometheus <br/>
- Scikit-learn <br/>

Neste semestre houve uma mudança na stack de tecnologias. O Vue JS foi a biblioteca utilizada na construção de páginas, e a linguagem Java, junto com o Spring e Hibernate, foram utilizadas no desenvolvimento das API's e serviços.
Isso proporcionou uma mudança na arquitetura da ferramenta.

### Contribuições pessoais

Minha atuação neste projeto foi focada nas criações de cenários de indisponibilidade e testes para geração de dados.
A serviço oferecido pela Orbit se baseia no aprendizado de máquina proporcionado por estes testes, onde diferentes características da saúde do serviço monitorado devem ser considerados. <br>
Utilizei ferramentas de teste em carga, como o [Locust.io](http://locust.io/), e ao mesmo tempo aplicações de monitoramento para relacionar estados como (consumo de recursos como CPU, memória, tempo de resposta, latência considerando a rede, etc) com o nível de estresse da aplicação monitorada. Além do trabalho de relacionar estes dados em estruturas que pudessem ser utilizadas por modelos de aprendizado de máquina.<br>
Com isso, minhas contribuições foram focadas na criação dos testes, para que pudessem representar o funcionamento de uma aplicação em diferentes cenários. Em coletar os dados do monitoramento da aplicação durante os testes, incluindo informações de monitoramente que pudessem medir diferentes aspectos da saúde da aplicação, e em armazenar estas métricas para alimentar de forma útil nosso modelo de maching learning, que se baseará na extrapolação dos dados no tempo para prever possíveis indisponibilidades. <br> <br>
O Scikit-learn foi utilizado realizando duas tarefas principais:<br>

- Utilizar os dados de saúde da aplicação e extrapolá-los no tempo, para que se pudesse ter uma estimativa no futuro de como estas métricas estariam.<br>
- Com os dados extrapolados, aplicar uma árvore de decisão para definir se naquele ponto no tempo, haveria risco futuro próximo de cenários de indisponibilidade.

## Aprendizados Efetivos HS

- Monitoramento de atributos de performance de aplicações web: Sei fazer com autonomia;
- Coleta e tratamento de dados para uso em bibliotecas de aprendizado de máquina: Sei fazer com autonomia;
- Desenvolvimento de API's com Spring Boot: Sei fazer com autonomia.

## Contatos:

- [LinkedIn;](https://www.linkedin.com/in/kau%C3%A3-borgarelli-5bb67220a/)
- [GitHub.](https://github.com/Borgarelli)
