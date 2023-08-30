# Projeto 3: 1º semestre de 2022

### Parceiro Acadêmico

MidAllº [B] 

![MidAll](https://user-images.githubusercontent.com/79945984/225166828-fd8d6942-68e5-4c26-9466-06bc7b08e0d0.png)

### *MidAllº [B]*

### Visão do Projeto
<p align = "justify">
Plataforma para Geração de Promoções em E-commerce: Flexibilidade e Agilidade

Apresentamos uma ferramenta destinada à criação de promoções no âmbito do E-commerce, onde as mecânicas promocionais são configuradas com flexibilidade, permitindo uma ágil adaptação conforme necessário. As regras promocionais são cadastradas e, posteriormente, implementadas pelo usuário quando produtos que a compõem são adicionados a sacola.

Atualmente, disponibilizamos o cadastro de produtos vinculados a promoções no servidor/banco de dados. Utilizando operadores lógicos, criamos diferentes mecânicas promocionais. Os descontos são aplicados na sacola de compras e contam com uma visualização específica para revisão e seleção de promoções.

Além disso, concedemos aos usuários a autonomia para gerir sua sacola, podendo editar, remover, arquivar ou reativar produtos. Similarmente, é possível editar, excluir, interromper ou ativar promoções. A visualização das promoções e produtos cadastrados é feita de maneira intuitiva através de uma lista com opção de filtragem, tornando possível a verificação dos estados de cada item.

</p>

Para acessar o vídeo de demonstração da aplicação em uso, clique [aqui](https://youtu.be/NhDe9-Z_dvk)

[<img src="https://github.com/DolphinDatabase/DescontOn/blob/47f0f23ee3d7710b472fc1ff26d06da50237681e/Imagens/imagem_2022-04-15_155641874.png" width="40%">](https://youtu.be/NhDe9-Z_dvk "DescontOn vídeo Demonstração")

### *Demonstração Descont0n*

Link do repositório do projeto: https://github.com/DolphinDatabase/DescontOn

## Tecnologias utilizadas 💻 

### JQuery <a href="https://jquery.com" target="_blank"><img width="65" height="20" src="https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white"/></a>

jQuery é uma biblioteca JavaScript criada por John Resig em 2006. É como um software de código aberto: seu uso é licenciado pela Massachusetts Institute of Technology (MIT) e pelo GNU General Public License (GPL). E essa biblioteca têm como principal finalidade associar-se aos elementos JavaScript em HTML para conferir mais dinamismo e usabilidade às páginas na internet.

Clique [aqui](https://jquery.com/), para acessar a documentação oficial.


### Thymeleaf <a href="https://www.thymeleaf.org" target="_blank">![Thymeleaf](https://img.shields.io/badge/Thymeleaf-darkgreen?style=flat-square&logo=thymeleaf)</a>

O Thymeleaf é um template engine voltado para projetos Java que facilitam a criação de páginas HTML. Permitindo a troca de informações entre o código Java e as páginas HTML.
De tal maneira garantindo que o desenvolvedor consiga criar templates de forma mais simples e de uma maneira mais agilizada para suas aplicações.

Clique [aqui](https://www.thymeleaf.org/), para acessar a documentação oficial.

### Spring Boot <a href="https://spring.io/projects/spring-boot" target="_blank"><img src="https://img.shields.io/badge/Spring-6DB33F?style=flat-square&logo=spring&logoColor=white"/></a>

O Spring Boot é um framework Java open source que tem como objetivo facilitar esse processo em aplicações Java. Trazendo mais agilidade para o processo de desenvolvimento com uma infinidade de ferramentas surge todos os dias visando justamente acelerar o processo de criação e implantação de soluções nos mais
variados ambientes.

Clique [aqui](https://spring.io/projects/spring-boot), para acessar a documentação oficial.

### Bootstrap <a href="https://getbootstrap.com" target="_blank"><img src="https://img.shields.io/badge/Bootstrap-563D7C?style=flat-square&logo=bootstrap&logoColor=white"/></a><br/>

O Bootstrap é um framework front-end que veio para facilitar e agilizar o trabalho, oferecendo padrões para HTML, JavaScript e CSS de acordo com o site CiaWebsites. O Bootstrap foi desenvolvido por Jacob Thorton e Mark Otto com o objetivo de facilitar a programação de um site web e otimizar seu desempenho.

Clique [aqui](https://getbootstrap.com/), para acessar a documentação oficial.

### Maven [![Maven](https://img.shields.io/badge/Maven-%23C71A36?style=for-the-badge&logo=apache-maven&logoColor=white)](https://maven.apache.org/)

O Apache Maven é uma ferramenta que oferece automação e gerenciamento de projetos Java (mas podem ser utilizada com outras linguagens), padronizando a construção e publicação de suas aplicações. Por ser extremamente flexível agrega agilidade e qualidade ao produto, além de permitir que sejam adicionados plugins a si e estender suas funcionalidades.

Clique [aqui](https://maven.apache.org/), para acessar a documentação original.

## Contribuições pessoais ✔

Neste projeto, desempenhei o papel da criação e gestão do banco de dados que serviu como a base para toda a aplicação. Para isso, foi necessário dedicar-me a um estudo aprofundado sobre a utilização do Oracle Database, um Sistema de Gerenciamento de Banco de Dados (SGBD) com o qual não possuía experiência prévia. Este SGBD apresenta uma sintaxe distinta dos mais comuns, como MySql e Postgres, exigindo um aprendizado específico para sua utilização eficaz.

Além disso, fiquei responsável pelo desenvolvimento web de algumas telas. Uma dessas telas foi a tela "Sacola", que têm o objetivo de exibir todos os produtos inseridos no nosso banco de dados, independentemente de serem dados fictícios ou fornecidos pelo próprio usuário. Outra tela mecessária foi a tela de "Cadastro de Produtos", que permite ao usuário inserir novos produtos e promoções, os quais seram posteriormente exibidos na tela de "Sacola".

<details><summary>Tela Sacola de Compras</summary>
<img src="https://github.com/Borgarelli/Portfolio-Fatec/assets/79945984/d788a696-8ab8-4ee8-a13b-b6c383d6db56">


> Aqui um trecho da creiação da tela Sacola de compras, onde o usuário têm um design amigável com botôes para editar, adicionar a sacola e mais algumas funcionalidades
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

<details><summary>Tela de Cadastro de Produtos</summary>
<img src="https://github.com/Borgarelli/Portfolio-Fatec/assets/79945984/1aff2e89-2c44-497e-a01e-76a631f9a14b">

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
Por conta desta experiência, fui inserido a um novo nível de exigência para a construção de um sistema web, tendo que me preocupar com o formato e conteúdo específico das requisições de possiveis entradas no serviço desenvolvido.

Além disso, aprendi muito sobre uma área não diretamente relacionada a tecnologias de construção de software, mas que eram essenciais para cumprir com as regras fornecidas pelo cliente, sejam elas em vendas, aplicações de descontos e regras de negócio, é algo que nunca pensei em trabalhar em conjunto antes. Esta habilidade de aprender de forma ágil sobre temas que sequer pensei em trabalhar, por conta das infinitas possíveis áreas de atuação de possíveis futuros clientes, foi de um valor excepcional para mim e para minha formação como aluno da Fatec.

- Criação de banco de dados para armazenamento de produtos cadastrados e novas regras geradas pelo usuário/cliente: sei fazer com autonomia
- Modelagem completa para armazenar todos os dados fornecidos e requisitados pelo usuário e pela aplicação: sei fazer com autonomia
- Desenvolvimento Web utilizando Bootstrap: sei fazer com auxilio

## Navegação Entre Projetos :link:
 
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Julius.md">1º Semestre: Julius - Assistente virtual criado para facilitar a sua vida financeira.</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/SGBD_Health.md"> 2º Semestre: SGBD Health - Aplicação de monitoramento de SGBD, foco em performance e desempenho</a></li></p>
<p align="justify" style="font-family:roboto;"><li>3° Semestre: Descont0n - Ferramenta para criação de promoções e regras de negócio com foco em E-commerce</li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/MCS.md"> 4° Semestre: MCS - Sistema ERP que visa gerenciar e controlar dados fornecidos pelos clientes</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/TechNinjas.md"> 5° Semestre: TECH NINJAS - Sistema de automatização fluxo de controle dos arquivos armazenados em cloud</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/README.md"> Voltar para página inicial</a></li></p>
