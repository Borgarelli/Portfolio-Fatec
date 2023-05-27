# Projeto 3: 3º semestre de 2022

### Parceiro Acadêmico
MidAll [B] </br>

![MidAll](https://user-images.githubusercontent.com/79945984/225166828-fd8d6942-68e5-4c26-9466-06bc7b08e0d0.png)

### *Figura 05. MidAllº*

### Visão do Projeto
<p align = "justify">
Ferramenta para criar promoções de E-commerce, onde as mecânicas de promoções são feitas de forma flexível e de rápida atualização no sistema. As regras de promoções são cadastradas e posteriormente aplicadas no momento em que os itens são adicionados ao carrinho.

Atualmente implementamos e apresentamos o cadastro dos produtos dentro de promoções registradas dentro do servidor/banco de dados, utilizando operadores lógicos para criar diferentes mecânicas de promoções, os descontos são aplicados dentro da sacola de compras e possui uma visualização dedicada para conferência e escolha de promoções.

Além disso, há a autonomia fornecida ao usuário para editar, remover, arquivar ou desarquivar seus produtos e também para editar, deletar, interromper ou ativar promoções de uma visualização de maneira prática e intuitiva dos produtos e promoções cadastradas através da listagem que possui um filtro para que seja possível diferenciar e verificar os status dos produtos e promoções.
</p>

Para acessar o vídeo de demonstração da aplicação em uso, clique [aqui](https://youtu.be/NhDe9-Z_dvk):

[<img src="https://github.com/DolphinDatabase/DescontOn/blob/47f0f23ee3d7710b472fc1ff26d06da50237681e/Imagens/imagem_2022-04-15_155641874.png" width="40%">](https://youtu.be/NhDe9-Z_dvk "DescontOn vídeo Demonstração")

### *Figura 04. Aplicação em ação - Motor de regras integrado a um E-commerce, realizando todo o processo de cadastro de novos produtos e o processo de criação de novas regras de desconto para aplicar a seus produtos*

Link do repositório do projeto: https://github.com/DolphinDatabase/DescontOn

## Tecnologias utilizadas

### JQuery <a href="https://jquery.com" target="_blank"><img width="65" height="20" src="https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white"/></a>

jQuery é uma biblioteca JavaScript criada por John Resig em 2006. É como um software de código aberto: seu uso é licenciado pela Massachusetts Institute of Technology (MIT) e pelo GNU General Public License (GPL). Sua principal finalidade é associar-se aos elementos JavaScript em HTML para conferir mais dinamismo e usabilidade às páginas na internet.

Suas linhas de código simplificam os scripts interpretados pelo navegador do client-side e por esse motivo é uma das bibliotecas mais populares na comunidade de desenvolvedores.

Clique [aqui](https://jquery.com/) para acessar a documentação oficial.


### Thymeleaf <a href="https://www.thymeleaf.org" target="_blank">![Thymeleaf](https://img.shields.io/badge/Thymeleaf-darkgreen?style=flat-square&logo=thymeleaf)</a>

O Thymeleaf é uma template engine voltado para projetos Java que facilitam a criação
de páginas HTML. Permitindo a troca de informações entre o código Java e as páginas
HTML, de tal maneira garantindo que o desenvolvedor consiga criar templates de
forma mais simples e de uma maneira mais agilizada para suas aplicações.

Clique [aqui](https://www.thymeleaf.org/) para acessar a documentação oficial.

### Spring Boot <a href="https://spring.io/projects/spring-boot" target="_blank"><img src="https://img.shields.io/badge/Spring-6DB33F?style=flat-square&logo=spring&logoColor=white"/></a>

O Spring Boot é um framework Java open source que tem como objetivo
facilitar esse processo em aplicações Java. Trazendo mais agilidade para o processo
de desenvolvimento com uma infinidade de ferramentas surge todos os dias visando
justamente acelerar o processo de criação e implantação de soluções nos mais
variados ambientes.

Clique [aqui](https://spring.io/projects/spring-boot) para acessar a documentação oficial.

### Bootstrap <a href="https://getbootstrap.com" target="_blank"><img src="https://img.shields.io/badge/Bootstrap-563D7C?style=flat-square&logo=bootstrap&logoColor=white"/></a><br/>

O Bootstrap é um framework front-end que veio para facilitar e agilizar o
trabalho, oferecendo padrões para HTML, JavaScript e CSS de acordo com o site
CiaWebsites. Foi desenvolvido por Jacob Thorton e Mark Otto com o objetivo de
facilitar a programação de um site web e otimizar o desempenho.

Clique [aqui](https://getbootstrap.com/) para acessar a documentação oficial.

### Maven [![Maven](https://img.shields.io/badge/Maven-%23C71A36?style=for-the-badge&logo=apache-maven&logoColor=white)](https://maven.apache.org/)

O Apache Maven é uma ferramenta que oferece automação e gerenciamento
de projetos Java (mas podem ser utilizada com outras linguagens), padronizando a
construção e publicação de suas aplicações. Por ser extremamente flexível agrega agilidade e qualidade ao produto, além de permitir que sejam adicionados plugins a si e estender suas funcionalidades.

Clique [aqui](https://maven.apache.org/) para acessar a documentação original.

## Contribuições pessoais

Neste projeto, desempenhei o papel da criação e gestão do banco de dados que serviu como a base para toda a aplicação. Para isso, foi necessário dedicar-me a um estudo aprofundado sobre a utilização do Oracle Database, um Sistema de Gerenciamento de Banco de Dados (SGBD) com o qual não possuía experiência prévia. Este SGBD apresenta uma sintaxe distinta dos mais comuns, como MySql e Postgres, exigindo um aprendizado específico para sua utilização eficaz.

Além disso, fiquei responsável pelo desenvolvimento web de algumas telas. Uma dessas telas foi a "Lista", que tinha o objetivo de exibir todos os produtos cadastrados no banco de dados, independentemente de serem dados fictícios ou inseridos pelo próprio usuário. Outra tela relevante foi a de "Cadastro de Produtos", que permitia ao usuário inserir novos produtos e promoções, os quais seriam posteriormente exibidos na tela de "Lista".

<details><summary>Tela da Lista de Compras</summary>

> Aqui o trecho de como foi programada a tela da Lista, a estilização foi feita tanto usando o BootStrap como estilização manual com css com auxilio do figma

```kotlin
<!-- TABELA -->
	<div class="container">
		<select name="op" id="op" class="form-select mb-2" onchange="changeTable()">
			<option value="0">Disponível</option>
			<option value="1">Arquivado</option>
		</select>
		<div class="table-responsive">
			<table class="table table-striped table-hover table-sm">
				<thead>
					<tr>
						<!-- nome das colunas -->
						<th>#</th>
						<th>Nome do Produto</th>
						<th>Categoria</th>
						<th>Valor de Venda</th>
						<th></th>
						<th></th>
						<th></th>
					</tr>
				</thead>
				<tbody id="disp">
				</tbody>
				<tbody id="arqui" style="display: none;">
				</tbody>
		</div>
	</div>
	</section>


	<!-- end tabela -->

	<!--  MODAL -->
	<div id="myModal" class="modal" tabindex="-1" role="dialog">
		<div class="modal-dialog" role="document">
			<div class="modal-content">
				<div class="modal-header">
					<h5 class="modal-title">Deletar Produto</h5>
				</div>
				<div class="modal-body">
					<p>Deseja realmente deletar o produto?</p>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-primary" onclick="excluirProduto()">Sim</button>
					<button type="button" class="btn btn-secondary"
						onclick="$('#myModal').modal('hide')">Cancelar</button>
				</div>
			</div>
		</div>
	</div>
```
</details>

Também fiquei responsável por criar e configurar a tela de cadastro de produtos e promoções sendo ambos registrados no banco criado no SGBD Oracle

<details><summary>Tela de Cadastro de produtos</summary>

> Aqui o trecho do desenvolvimento da tela de cadastro de produtos, feita em Html-5 e JavaScript, e a estilização feita tanto com o BootStrap como de maneira manual usando CSS-3 com auxilio do figma

```kotlin
<!-- FORMULARIO DE CADASTRO -->
<div class="layout-main">
  <section class="layout-content">
    <section class="layout-content">
      <div class="container" id="cadastro">
        <form class="needs-validation" id="main-form" novalidate onsubmit="saveProduto(event)">
          <div class="form-row">

            <!-- Nome -->
            <div class="form-group col-md-6">
              <label for="nome">Nome do Produto</label>
              <input type="text" class="form-control" id="proNome" placeholder="Nome" autofocus="autofocus" value="" required />
              <div class="invalid-feedback">
                Por favor, informe o nome do produto.
              </div>
            </div>
          </div>

          <!-- Categoria -->
          <div class="form-row">
            <div class="form-group col-md-6">
              <label for="categoria">Categoria</label>
              <select class="form-select" id="proCategoria" aria-label="Default select example">
                <option value="Cosmeticos">Cosméticos</option>
                <option value="Perfumaria">Perfumaria</option>
                <option value="Saude">Saúde</option>
              </select>
            </div>
          </div>

          <!-- Valor -->
          <div class="form-row">
            <div class="form-group col-md-6">
              <label for="valor">Valor de Venda</label>
              <input type="text" class="form-control" id="proValor" placeholder="Valor de Venda" data-mask-reverse="true" value="" required />
              <div class="invalid-feedback">
                Por favor, insira o valor do produto.
              </div>
            </div>
          </div>

          <button type="submit" class="btn btn-primary btn-sm">Cadastrar</button>
        </form>
      </div>
    </section>
    <!-- end formulario -->

    <!--  MODAL -->
    <div id="myModal" class="modal" tabindex="-1" role="dialog">
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Criar Produto</h5>
          </div>
          <div class="modal-body">
            <p id="modalContent"></p>
          </div>
          <div class="modal-footer">
            <button type="button" id="modalClose" class="btn btn-primary">Ok</button>
          </div>
        </div>
      </div>
    </div>
    <!-- END MODAL -->
```
</details>

## Aprendizados Efetivos  ![Aprendizados efetivos](https://img.shields.io/badge/Aprendizados%20efetivos-100%25-brightgreen?style=for-the-badge)

No desenvolvimento das modelagens do nosso E-commerce, aprendi mais sobre a estruturação de um mesmo. Foi a primeira vez em que trabalhei de fato com uma aplicação front-end voltada principal para web.
Por conta desta experiência, fui inserido a um novo nível de exigência para a construção de um sistema web, tendo que me preocupar com o formato e conteúdo específico das requisições de entrada possiveis no serviço desenvolvido.

Além disso, aprendi muito sobre uma área não diretamente relacionada a tecnologias de construção de software, mas que eram essenciais para cumprir com as regras informadas pelo cliente, sejam elas em vendas, aplicações de descontos e regras de negócio, é algo que nunca pensei em trabalhar em conjunto antes. Esta habilidade de aprender de forma ágil sobre temas que sequer pensei em trabalhar, por conta das infinitas possíveis áreas de atuação de possíveis futuros clientes, foi de um valor excepcional para mim e para minha formação como aluno da Fatec.

- Criação de banco de dados para armazenamento de produtos cadastrados e novas regras geradas pelo usuário/cliente: sei fazer com autonomia
- Modelagem completa para armazenar todos os dados oferecidos e requisitados pelo usuário e pela aplicação: sei fazer com autonomia
- Desenvolvimento Web utilizando Bootstrap: sei fazer com auxilio

## Navegação Projetos :link:
 
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Julius.md">1º Semestre: Julius - Assistente virtual criado para facilitar a sua vida financeira.</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/SGBD_Health.md"> 2º Semestre: SGBD Health - Aplicação de monitoramento voltada para SGBDs, focada na performance e desempenho.</a></li></p>
<p align="justify" style="font-family:roboto;"><li>3° Semestre: Descont0n - Ferramenta para criação de promoções e regras de negócio com foco em E-commerce</li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/MCS.md"> 4° Semestre: MCS - Um sistema ERP que visa gerenciar e controlar dados fornecidos pelos usuários clientes</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/GabrielSG20/Portfolio/blob/main/API_5.md"> 5º Semestre: Data Rangers - Ferramenta de análise de dados para prospecção de novos clientes</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/GabrielSG20/Portfolio/blob/main/API_6.md"> 6º Semestre: D-end - Processamento e análise de dados para tratamento de inconsistências</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/README.md"> Voltar para página inicial</a></li></p>