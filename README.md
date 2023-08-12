<p align="center" dir="auto">
<p dir="auto"><a target="_blank" rel="noopener noreferrer nofollow" href="https://camo.githubusercontent.com/29e7fc6c62f61f432d3852fbfa4190ff07f397ca3bde27a8196bcd5beae3ff77/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f706f7374677265732d2532333331363139322e7376673f7374796c653d666f722d7468652d6261646765266c6f676f3d706f737467726573716c266c6f676f436f6c6f723d7768697465"><img src="https://camo.githubusercontent.com/29e7fc6c62f61f432d3852fbfa4190ff07f397ca3bde27a8196bcd5beae3ff77/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f706f7374677265732d2532333331363139322e7376673f7374796c653d666f722d7468652d6261646765266c6f676f3d706f737467726573716c266c6f676f436f6c6f723d7768697465" alt="Postgres" data-canonical-src="https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&amp;logo=postgresql&amp;logoColor=white" style="max-width: 100%;"></a> <a target="_blank" rel="noopener noreferrer nofollow" href="https://camo.githubusercontent.com/d10e346678b885e7ebed0f04e8a2e0874c276520997b070623819cfea2f02d8a/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f706f7765725f62692d4632433831313f7374796c653d666f722d7468652d6261646765266c6f676f3d706f7765726269266c6f676f436f6c6f723d626c61636b"><img src="https://camo.githubusercontent.com/d10e346678b885e7ebed0f04e8a2e0874c276520997b070623819cfea2f02d8a/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f706f7765725f62692d4632433831313f7374796c653d666f722d7468652d6261646765266c6f676f3d706f7765726269266c6f676f436f6c6f723d626c61636b" alt="Power Bi" data-canonical-src="https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&amp;logo=powerbi&amp;logoColor=black" style="max-width: 100%;"></a> <a target="_blank" rel="noopener noreferrer nofollow" href="https://camo.githubusercontent.com/cb65948f8e29e529c38c9aabc8168c84a352670c51198750a6ef297a7a44b4e8/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f53514c2d2532333030373538462e7376673f7374796c653d666f722d7468652d6261646765266c6f676f3d73716c266c6f676f436f6c6f723d7768697465"><img src="https://camo.githubusercontent.com/cb65948f8e29e529c38c9aabc8168c84a352670c51198750a6ef297a7a44b4e8/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f53514c2d2532333030373538462e7376673f7374796c653d666f722d7468652d6261646765266c6f676f3d73716c266c6f676f436f6c6f723d7768697465" alt="SQL" data-canonical-src="https://img.shields.io/badge/SQL-%2300758F.svg?style=for-the-badge&amp;logo=sql&amp;logoColor=white" style="max-width: 100%;"></a> <a target="_blank" rel="noopener noreferrer nofollow" href="https://camo.githubusercontent.com/f77444a2482b5f5837b46ecb1a88d208875744b65f5b40a86dd8284b42f497db/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f45544c2d70696e6b3f7374796c653d666f722d7468652d6261646765266c6f676f3d73716c266c6f676f436f6c6f723d7768697465"><img src="https://camo.githubusercontent.com/f77444a2482b5f5837b46ecb1a88d208875744b65f5b40a86dd8284b42f497db/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f45544c2d70696e6b3f7374796c653d666f722d7468652d6261646765266c6f676f3d73716c266c6f676f436f6c6f723d7768697465" alt="ETL" data-canonical-src="https://img.shields.io/badge/ETL-pink?style=for-the-badge&amp;logo=sql&amp;logoColor=white" style="max-width: 100%;"></a>
</p>
</div>

# Banco de Dados RH

No Case abaixo, vamos mergulhar em um breve estudo na estruturação de um Banco de Dados da área de Rh de uma organização.

Considerando que já temos as Modelagens Conceitual e Lógica, vamos partir diretamente para o desenvolvimento do Modelo Físico e do Banco de Dados.

Pelas informações obtidas, teremos as seguintes entidades para serem desenvolvidas

| Tabela       | Descrição no BD |
|--------------|-----------------|
| Departamento      | tb_departamento           |
| Funcionarios      | tb_funcionarios          |


Tabela Departamento (tb_departamento )
| Coluna        | Tipo          |
|---------------|---------------|
| id_departamento (pk)    |     integer PRIMARY KEY          |
| nm_departamento        |      varchar(100)         |
| local_departamento         |      varchar(100)         |
| codigo_departamento         |      integer         |

Tabela Funcionarios (tb_departamento )
| Coluna        | Tipo          |
|---------------|---------------|
| id_funcionario (pk)    |     integer PRIMARY KEY          |
| nm_funcionario         |      varchar(100)         |
| cargo_funcionario         |      varchar(100)         |
| salario_funcionario        |      decimal(19,2)         |
| id_departamento         |      integer         |


## 1. Desenvolvendo o Modelo Físico e Criando o Banco de Dados

CREATE DATABASE Empresa_RH

## 1.1 Criando a tabela tb_departamento

```sql
CREATE TABLE IF NOT EXISTS tb_departamento (
	id_departamento integer PRIMARY KEY,
	nm_departamento varchar(100),
	local_departamento varchar(100),
	codigo_departamento integer
)
```

## 1.2 Criando a tabela tb_funcionarios

```sql
CREATE TABLE IF NOT EXISTS tb_funcionarios (
	id_funcionario integer PRIMARY KEY,
	nm_funcionario varchar(100),
	cargo_funcionario varchar(100),
	salario_funcionario decimal(19,2),
	id_departamento integer references tb_departamento (id_departamento)
)
```

## 2 Alterando alguns campos da Tabela para adequar a melhor necessidade

## 2.1 Alterando o tipo de dado do campo Código do Departamento da tabela tb_departamento

```sql
ALTER TABLE tb_departamento 
	ALTER COLUMN codigo_departamento TYPE varchar(10);
```

## 3 Inserindo dados nas Tabelas

Agora com o banco de dados criado, podemos inserir as infromações no sistema por diversas formas, como por exemplo
• Documentos e registros em sistemas em ambiente visual/software;
• Através de Formulários e planilhas;
• Entrevistas e Questionários e levantamentos;
• Planilhas, entre outros;

Dessa forma, para testar o banco e tabelas criadas, vamos popular algumas tabelas para praticar algumas funções INSERT.

## 3.1 Inserindo 10 novos funcionários no banco de dados e 5 departamentos 

```sql
-- Criando 5 departamentos (DML)
INSERT INTO tb_departamento 	(id_departamento, nm_departamento, local_departamento, codigo_departamento) 
						VALUES 	(1,'RH','Fortaleza','DEP01');
INSERT INTO tb_departamento 	(id_departamento, nm_departamento, local_departamento, codigo_departamento) 
						VALUES 	(2,'Diretoria','Fortaleza','DEP02');
INSERT INTO tb_departamento 	(id_departamento, nm_departamento, local_departamento, codigo_departamento) 
						VALUES 	(3,'Comercial','Fortaleza','DEP03');
INSERT INTO tb_departamento 	(id_departamento, nm_departamento, local_departamento, codigo_departamento) 
						VALUES 	(4,'Marketing','Fortaleza','DEP04');
INSERT INTO tb_departamento 	(id_departamento, nm_departamento, local_departamento, codigo_departamento) 
						VALUES 	(5,'Engenharia','Fortaleza','DEP05');

-- Consultando a tabela de Departamentos (DQL)
SELECT * FROM tb_departamento;
```

```sql
-- Inserindo 10 funcionarios (DML)
INSERT INTO tb_funcionarios (id_funcionario, nm_funcionario, cargo_funcionario,	salario_funcionario, id_departamento) 
					VALUES	(01,'FUNCIONARIO A','DIRETOR',20000.00,2),
							(02,'FUNCIONARIO B','GERENTE COMERCIAL',5000.00,3),
							(03,'FUNCIONARIO C','CONSULTOR DE VENDAS',2000.00,3),
							(04,'FUNCIONARIO D','CONSULTOR DE VENDAS',2000.00,3),
							(05,'FUNCIONARIO E','CONSULTOR DE VENDAS',2000.00,3),
							(06,'FUNCIONARIO F','GERENTE DE INOVACAO',5000.00,5),
							(07,'FUNCIONARIO G','DESENVOLVEDOR FULL STACK',5000.00,5),
							(08,'FUNCIONARIO H','ASSISTENTE DE MARKETING',2000.00,4),
							(09,'FUNCIONARIO I','GERENTE DE RH',5000.00,1),
							(10,'FUNCIONARIO J','ASSISTENTE DE RH',2000.00,1);
```

## 3.2  Atualizar o salário de um funcionário via Banco de Dados

Para praticar a alteração de dados direto no Banco de Dados através do SQL, podemos considerar o seguinte código:

```sql
-- Atualizando o salário do FUNCIONARIO F GERENTE DE INOVACAO (DML) - Data Manipulation Language
UPDATE tb_funcionarios
  SET salario_funcionario = 8000.00
  WHERE id_funcionario = 06;
```

## 4 Insights e Análise dos Dados

Podemos utilizar alguns scripts SQL na funçaõ SELECT * FROM para obter insights e realizar algumas análise de dados.
A seguir, apresentamos alguns exemplos de como obter insights dos registros feitos no Banco de Dados.

## 4.1 Recuperar todos os funcionários de um determinado departamento.

-- Consultando a tabela de Funcionários do departamento Comercial, RH e Engenharia (DQL)
SELECT 	tb_fun.*
		, tb_dep.nm_departamento
		FROM tb_funcionarios tb_fun
		JOIN tb_departamento tb_dep ON tb_dep.id_departamento = tb_fun.id_departamento
		WHERE  tb_dep.id_departamento IN (1,3,5);

## 4.2 Recuperar todos os funcionários que possuem salário maior que um valor especificado.

-- Consultando todos os funcionários que possuem salário maior ou igual a R$ 5.000,00
SELECT * FROM tb_funcionarios 
		WHERE  salario_funcionario >= 5000;

## 4.3 Recuperar o nome do departamento e o nome do funcionário que trabalha naquele departamento.

SELECT 	  nm_departamento AS Departamento
		, nm_funcionario AS Funcionario
		FROM      tb_departamento AS tb_dep 
		INNER JOIN tb_funcionarios AS tb_fun ON tb_fun.id_departamento = tb_dep.id_departamento;

## 4.4 Recuperar o nome do departamento e a média salarial dos funcionários de cada departamento. 

--A média salarial deve ser calculada para cada departamento individualmente.

SELECT 	tb_dep.nm_departamento
        , ROUND(AVG(salario_funcionario),2) AS Media_Salario
		FROM      tb_departamento AS tb_dep 
		LEFT JOIN tb_funcionarios AS tb_fun ON tb_fun.id_departamento = tb_dep.id_departamento
		GROUP BY tb_dep.nm_departamento;
		
## 4.5 Recuperar o nome e o salário dos 3 funcionários com os salários mais altos, ordenados em ordem decrescente de salário.

SELECT 	  --nm_departamento AS Departamento
		 nm_funcionario AS Funcionario
		, salario_funcionario AS Salario
		FROM      tb_departamento AS tb_dep 
		INNER JOIN tb_funcionarios AS tb_fun ON tb_fun.id_departamento = tb_dep.id_departamento
		ORDER BY salario_funcionario DESC
		LIMIT 3
		;

## 4.6 Recuperar o nome dos funcionários que trabalham em departamentos localizados em "São Paulo" e possuem um salário acima da média salarial de todos os funcionários.		

UPDATE tb_departamento
  SET local_departamento = 'Sao Paulo'
  WHERE id_departamento = 3;

SELECT * FROM tb_departamento;

SELECT 	--nm_departamento AS Departamento
		 nm_funcionario AS Funcionario
		--salario_funcionario AS Salario
		FROM      tb_departamento AS tb_dep 
		INNER JOIN tb_funcionarios AS tb_fun ON tb_fun.id_departamento = tb_dep.id_departamento
 		WHERE tb_dep.local_departamento = 'Sao Paulo' AND
			  tb_fun.salario_funcionario > (SELECT AVG(salario_funcionario) FROM tb_funcionarios)
			  ;

## 5. Considerações Finais

Bom, neste estudo sobre a estruturação de um Banco de Dados na área de Recursos Humanos (RH), foram apresentadas várias etapas e ações relacionadas ao desenvolvimento e gerenciamento do banco de dados. Foram fornecidos detalhes sobre a criação das tabelas "tb_departamento" e "tb_funcionarios", bem como exemplos de inserção de dados nessas tabelas.

No processo de criação do Modelo Físico e do Banco de Dados, foram discutidas as etapas de criação das tabelas "tb_departamento" e "tb_funcionarios" usando comandos SQL, incluindo a definição de tipos de coluna e chaves primárias, bem como a criação de relações entre as tabelas.

Além disso, houve uma seção dedicada a alterações na estrutura da tabela, destacando a alteração do tipo de dado de uma coluna específica na tabela "tb_departamento".

A seção subsequente tratou da inserção de dados nas tabelas, exemplificando como inserir departamentos e funcionários utilizando comandos SQL.

Outra parte relevante incluiu exemplos de consultas SQL para obter insights e realizar análises dos dados armazenados no banco. Foram apresentadas consultas que permitiram recuperar informações sobre funcionários de determinados departamentos, funcionários com salários acima de um valor especificado, médias salariais por departamento, os funcionários com os salários mais altos, entre outros.

O estudo concluiu ressaltando a importância de adquirir prática na manipulação de dados por meio de comandos SQL, evidenciando que o Banco de Dados de RH oferece oportunidades para análises profundas e tomadas de decisão informadas sobre a gestão de recursos humanos em uma organização.



Para mais informações ou detalhes, entre em contato através do [e-mail](engluizpolicarpo)


**Luiz Policarpo** (*Consultor em comércio exterior com experiência de mais de 13 anos no mercado, engenheiro de produção pós graduado em Supply Chain, Logística e Transportes, especializado em regimes aduaneiros especiais de importação e exportação, garantindo conformidade e excelência operacional.*) -  [LinkedIn](https://www.linkedin.com/in/luizpolicarpo/) | [Blog e Artigos](https://einship.com/blog-list) | [Instagram](https://instagram.com/luizpolicarpo)


