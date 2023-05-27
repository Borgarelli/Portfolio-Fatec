# Projeto 2: 2º semestre de 2021

### Parceiro Acadêmico

Necto Systems <br/>

![https://user-images.githubusercontent.com/74321890/200952858-ff867019-d4c6-49cf-9c2a-9508546a5ed9.png](https://user-images.githubusercontent.com/74321890/200952858-ff867019-d4c6-49cf-9c2a-9508546a5ed9.png)

### *Figura 01. Necto Systems*

### Visão do Projeto

<p align = "justify">
O SGBD HEalth é uma solução especializada para gerenciamento de Sistemas Gerenciadores de Banco de Dados (SGBDs). É projetado para monitorar e analisar os recursos do SGBD em tempo real como alertas, geração de relatórios personalizados e visualização de tendências históricas, permitindo que os administradores de banco de dados identifiquem rapidamente problemas críticos e tomem medidas corretivas imediatas.

Através da coleta de dados do SGBD, como memória, tempo de consultas, espaço em disco, transações, evolução da memória, caches e registros, o aplicativo fornece uma visão abrangente e detalhada do desempenho e da performance do SGBD. Esses dados são apresentados de maneira clara e intuitiva, facilitando a identificação de possíveis gargalos, problemas de desempenho e oportunidades de otimização.
</p>

Segue abaixo um video revelando o funcionamento do projeto: 

[<img src="https://user-images.githubusercontent.com/79945984/225161808-9c6c5ffa-ff60-48cb-8bce-95d81551aeb7.png" width="35%" height="10%">](https://youtu.be/NhDe9-Z_dvk "DescontOn vídeo Demonstração")

### *Figura 02. Demonstração SGBD Health*

Link do repositório do projeto: [https://github.com/DolphinDatabase/SGBD_Health](https://github.com/DolphinDatabase/SGBD_Health)

### Tecnologias utilizadas

### PostgreSQL [![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)

PostgreSQL é um sistema gerenciador de banco de dados objeto-relacional baseado no POSTGRES, Versão 4.2, desenvolvido na Universidade da Califórnia no Departamento de Ciências da Computação em Berkeley, o qual foi pioneiro em muitos conceitos que vieram a estar disponíveis em alguns bancos de dados comerciais mais tarde. O PostgreSQL é um banco de dados objeto-relacional (sem relação com linguagens de programação orientadas a objetos), em que cada coisa criada é tratada como um objeto, tais como bancos de dados, tabelas, views, triggers, etc.

Clique [aqui](https://www.postgresql.org/about/) para acessar a documentação oficial.
	
### SQlite [![SQLite](https://img.shields.io/badge/SQLite-%2307405e.svg?&style=for-the-badge&logo=sqlite&logoColor=white)](https://www.sqlite.org/)

SQLite é um sistema de gerenciamento de banco de dados relacional leve, embutido e amplamente utilizado em aplicativos móveis, navegadores da web e outros softwares que precisam armazenar dados localmente. Ele é uma biblioteca escrita em C que oferece recursos avançados de gerenciamento de banco de dados, como transações ACID, integridade referencial e indexação avançada, tornando-o uma escolha popular para desenvolvedores que precisam de uma solução de banco de dados confiável e fácil de usar

Clique [aqui](https://www.sqlite.org/about.html) para acessar a documentação oficial.

### Java [![Java](https://img.shields.io/badge/Java-%23ED8B00?style=for-the-badge&logo=java&logoColor=white&labelColor=%23ED8B00)](https://www.java.com/)

Java é uma linguagem de programação de alto nível, orientada a objetos e multiplataforma lançada em 1995 pela Sun Microsystems (agora Oracle). Ela é amplamente usada para desenvolver aplicativos, jogos, sistemas de gerenciamento de banco de dados, aplicativos da web e muito mais. Java é portátil, seguro, escalável e capaz de lidar com aplicativos complexos, com suporte de uma grande comunidade de desenvolvedores em todo o mundo.

Clique [aqui](https://www.java.com/pt-BR/download/help/whatis_java.html) para acessar a documentação oficial.
	
## Contribuições pessoais ![Contribuições pessoais](https://img.shields.io/github/commit-activity/y/Borgarelli/SGBD_Health?style=for-the-badge)

Durante minha participação no projeto, fui responsável pela modelagem do banco de dados no PostgreSQL e pela avaliação da utilização do SQLite para armazenamento de arquivos CSV. Trabalhei em estreita colaboração com a equipe de desenvolvimento para garantir a integração adequada do banco de dados com a aplicação e o sucesso do projeto.

Para garantir a estruturação adequada do banco de dados, dediquei tempo à elaboração do esquema de banco de dados e à escrita de scripts de criação e manipulação de tabelas, índices e outras estruturas relevantes para o projeto.

Além disso, busquei estudar conceitos e técnicas relevantes à implementação do banco de dados e outras funcionalidades da aplicação para garantir uma base sólida na gestão dos dados que atendesse aos requisitos e expectativas do projeto.
Segue abaixo um trecho da criação da tabela no SQLite:

<details> <summary>Banco criado pelo SQlite</summary>

> Aqui temos um trecho da conexão sendo criada com o SQlite para rodar um banco de dados de forma local para o armazenamento dos documentos em csv e arquivos gerados pela aplicação

```kotlin
import java.sql.*;
import java.time.LocalDateTime;
import java.util.ArrayList;

public class BancoSqlite extends Fileconnect {

	public static void bancoSqlite(String selectBd, String selectId, String insert, int r, int f) throws SQLException {

		LocalDateTime ldtNow = LocalDateTime.now(); // Trás a data e hora atual
		Fileconnect setar = new Fileconnect();

		String valor = "connectionBd";
		Connection conn = null;
		Statement stmt = null;

		// Conectando com banco da nossa aplicação
		try {
			String conexaoBancoDaApalicacao = setar.setarValor(valor);
			Class.forName("org.sqlite.JDBC");
			conn = DriverManager.getConnection(conexaoBancoDaApalicacao);

			// CREATE TABLE IF NOT EXISTS
			stmt = conn.createStatement();
			String sql = "CREATE TABLE IF NOT EXISTS SER_SERVIDOR " + "(SER_ID INT PRIMARY KEY     NOT NULL,"
					+ " SER_CONNECTION          TEXT   NOT NULL, " + " SER_USER            TEXT     NOT NULL, "
					+ " SER_PASS        TEXT )";
			stmt.executeUpdate(sql);

			String sql2 = "CREATE TABLE IF NOT EXISTS ARM_ARMAZENAMENTO "
					+ "(ID_ARMAZENAMENTO INT PRIMARY KEY     NOT NULL," 
					+ " ARM_BANCO            TEXT     NOT NULL, " + " ARM_TAMANHO        TEXT, "
					+ " ARM_DATA_HORA         DATETIME," + "ARM_SERVER    TEXT, " 
					+ " FOREIGN KEY (ARM_SERVER) REFERENCES SER_SERVIDOR (SER_ID))";
			stmt.executeUpdate(sql2);

			String sql3 = "CREATE TABLE IF NOT EXISTS QRY_QUERY " + "(QRY_ID INT PRIMARY KEY NOT NULL,"
					+ "QRY_QUERY_ID TEXT NOT NULL,"
					+ " QRY_NOME           TEXT    NOT NULL, " + " QRY_CALLS            INT     NOT NULL, "
					+ " QRY_TEMPO       TIME, " + " QRY_DATA_HORA         DATETIME, " + " QRY_SERVER         TEXT,"
					+ " FOREIGN KEY (QRY_SERVER) REFERENCES SER_SERVIDOR (SER_ID))";
			stmt.executeUpdate(sql3);
        }
    }
}
```
</details>

## Aprendizados Efetivos ![Aprendizados efetivos](https://img.shields.io/badge/Aprendizados%20efetivos-100%25-brightgreen?style=for-the-badge)
Este projeto marcou o início de uma verdadeira API com clientes parceiros da Fatec, proporcionando experiências incríveis e desafiadoras ao longo do semestre. O principal foco foi o desenvolvimento do banco de dados para atender a todos os requisitos necessários para a aplicação, permitindo o armazenamento de todos os dados necessários para os testes e também trabalhar com a ferrmenta do SQLite para desenvolver um banco local de maneira efetiva para testar as funcionalidades propostas pelo SGBD Health.

Este projeto foi de extrema importancia para meu desenvolvimento como programador, pois foi o primeiro contato com a linguagem de Java e um primeiro contato direto com clientes parceiros da Fatec, fornecendo diversas experiencias relevantes para meu curriculo profissional e pessoal 

- Utilização do PostgreSQL: sei fazer com autonomia.
- Criar tabelas, relacionamentos e modelagem: sei fazer com autonomia.
- Desenvolvimento de scripts em Java: sei fazer com auxilio.

## Navegação Projetos :link:
 
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/Julius.md"> 1º Semestre: Julius - Assistente virtual criado para facilitar a sua vida financeira.</a></li></p>
<p align="justify" style="font-family:roboto;"><li> 2º Semestre: SGBD Health - Aplicação de monitoramento voltada para SGBDs, focada na performance e desempenho.</li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/GabrielSG20/Portfolio/blob/main/API_3.md"> 3° Semestre: AirPLAN - O software que otimiza a criação e controle de documentos de aeronaves</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/GabrielSG20/Portfolio/blob/main/API_4.md"> 4° Semestre: #VEMPRACASA - Uma plataforma de gerenciamento de eventos</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/GabrielSG20/Portfolio/blob/main/API_5.md"> 5º Semestre: Data Rangers - Ferramenta de análise de dados para prospecção de novos clientes</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/GabrielSG20/Portfolio/blob/main/API_6.md"> 6º Semestre: D-end - Processamento e análise de dados para tratamento de inconsistências</a></li></p>
<p align="justify" style="font-family:roboto;"><li><a href="https://github.com/Borgarelli/Portfolio-Fatec/blob/main/README.md"> Voltar para página inicial</a></li></p>
  