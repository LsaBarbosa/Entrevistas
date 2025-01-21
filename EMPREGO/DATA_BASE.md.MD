# SQL
## Conceito
    - Organizado em estrutura tabular (tabelas / relacionamento)
    - Tabelas relacionadas entre si por meio de chaves estrangeiras e primárias
    
    * Integridade Relacional: Regras garantem a integridade dos dados
        - Chave primaria: garante que cada registro seja único na tabela
        - Chave estrangeira: Relaiona tabelas e mantém a consistencia referencial entre elas
## ACID
    - Atomicidade: A transação é completada totalmente ou não é feita
    - Consistencia: O Banco permanece num estado válido após uma transação
    - Isolamento: Transações paralelas nao interferem entre si
    - Durabilidade: Dados perssitem mesmo após falha
## Joins
### Resumo
    JOIN	Comportamento
    INNER	Apenas registros correspondentes entre as tabelas.
    LEFT	Todos os registros da tabela esquerda, com NULL para não correspondentes.
    RIGHT	Todos os registros da tabela direita, com NULL para não correspondentes.
    FULL	Todos os registros de ambas as tabelas, preenchendo com NULL onde necessário.
    CROSS	Produto cartesiano de ambas as tabelas.
    SELF	Join entre uma tabela e ela mesma.
### Exemplos
    - INNER: Registros correspondente nas tabelas envolvidas
```text
EXEMPLO INNER
SELECT clientes.nome, pedidos.id, pedidos.valor
FROM clientes
INNER JOIN pedidos ON clientes.id = pedidos.cliente_id;

tabela cliente tem id e nome
tabela pedidos tem id e valor
Nova tabela nome,id e valor
```

    - LEFT: Todos registros da tabela da esquerda e os correspondente da direita
        - Não havendo correspondencia na tabela a direita retorna como null

    * Obs Para o Rigth Join é a mesma logica soque com a tabela da direita
```text
EXEMPLO LEFT
SELECT clientes.nome, pedidos.id, pedidos.valor
FROM clientes
INNER JOIN pedidos ON clientes.id = pedidos.cliente_id;

tabela cliente tem id e nome
id , nome
1     Joao
2     Maria

tabela pedidos tem id e valor
id , cliente.id valor
101    1         100
102    1         200

Nova tabela nome,id e valor
nome,id valor
joao  101  100
joao  102  200
maria  null null
```

    - FULL JOIN: Combina todos os registros de todas as tabelas, null onde nao tiver correspondencia
```text
EXEMPLO FULL
SELECT clientes.nome, pedidos.id, pedidos.valor
FROM clientes
INNER JOIN pedidos ON clientes.id = pedidos.cliente_id;

tabela cliente tem id e nome
id , nome
1     Joao
2     Maria

tabela pedidos tem id e valor
id , cliente.id valor
101    1         100
102    2         200

Nova tabela nome,id e valor
nome,id valor
joao  101  100
maria  null  null
null  102   200
```
## Querys
```text - BUSCA BÁSICA
SELECT * FROM clientes; todos os dados da tabela
SELECT nome, email FROM clientes; Colunas específicas
SELECT nome, email FROM clientes WHERE cidade = 'São Paulo'; Filtro por dado específico
SELECT nome, email FROM clientes ORDER BY nome ASC; Ordedando busca -- ASC para crescente, DESC para decrescente
SELECT nome, email FROM clientes LIMIT 5; Limita o resultado-- Mostra apenas os primeiros 5 registros

```
```text - CONDICIONAL
SELECT * FROM pedidos
WHERE valor > 500 AND status = 'Enviado';

SELECT * FROM pedidos
WHERE status = 'Pendente' OR valor > 1000;

SELECT * FROM clientes
WHERE cidade IN ('São Paulo', 'Rio de Janeiro', 'Belo Horizonte');

SELECT * FROM pedidos
WHERE data BETWEEN '2025-01-01' AND '2025-01-31';

SELECT * FROM clientes
WHERE nome LIKE 'Jo%'; -- Nomes que começam com 'Jo'

```
```text FUNÇÔES AGREGADA
SELECT COUNT(*) AS total_clientes FROM clientes; conta os registros

SELECT SUM(valor) AS total_vendas FROM pedidos; soma os valores dos registros

SELECT AVG(valor) AS media_vendas FROM pedidos; media dos valores do registro

SELECT MAX(valor) AS maior_pedido, MIN(valor) AS menor_pedido FROM pedidos; Maior, Menor valor 

```
```text AGRUPAMENTO
SELECT cidade, COUNT(*) AS total_clientes
FROM clientes GROUP BY cidade; Agrupando dados

SELECT cidade, COUNT(*) AS total_clientes
FROM clientes GROUP BY cidade
HAVING COUNT(*) > 10; -- Mostra apenas cidades com mais de 10 clientes| Filtra resultados

```

# NoSQL
## Conceito
    - Não usa Tabelas, linhas, colunas como estrutura principal
    - Dados em formas de documentos, pares chave-valor, grafos, ou colunas amplas
    
    * Caracteristica NoSQL
    - Flexibilidade: Pode armazenar dados estruturados, semi-estruturados, e nao estruturados
    - Escalabilidade Horizontal: Adiciona mais servidores para lidar com mais dados
    - Performance alta escala: Otimizado para leitura e escrita rápida, mesmo com grande volume de dados
## Tipos De NoSql
    - Orientado a Documentos
        * Dados no formato JSON, BSON, XML
        * Pode conter diferentes campos e estruturas, permitindo flexibilidade
        * MONGODB, COUCHBASE, AMAZON DOCUMENTDB

    - Chave - Valor
        * Dados no padrão chave-valor, onde a chave é unica e usada para acessar o valor
        * Rápido e simples, são ideais para caching e armazenamentos simples
        * REDIS, AMAZON DYNAMODB, MEMCACHED
```text
chave: cliente:1
valor: {"nome": "Maria", "cidade": "São Paulo"}
```
    - Grafo (Graph DataBase)
        * Dados em forma de nós e arestas, representando entidades e seus relacionamentos
        * Modelar redes sociais, sistema de recomendação e análise de redes
        * NEO4J, ARANGODB, AMAZON NEPTUNE
## Exemplos
```text -> APLICAÇÂO 
Banco	|       Tipo	    |   Caso de Uso Principal
MongoDB	|       Documento	|   Aplicações web, dados flexíveis, logs
Redis	|       Chave-Valor	|   Cache, filas, sessões
Neo4j	|       Grafo	    |   Redes sociais, sistemas de recomendação
Apache  |       Cassandra	|   Colunas Amplas	Data warehouses, IoT, grandes volumes de dados
DynamoDB|	Chave-Valor/Doc |	Sistemas altamente escaláveis e servidores
HBase	|   Colunas Amplas	|   Grandes volumes de dados distribuídos
```

# SQL vs NOSQL
```text
Aspecto         	                Relacional	                      Não Relacional
Modelo de Dados	            Estruturado (tabelas, colunas, linhas)	    Flexível (documentos, grafos, etc.)
Esquema	                                Estrito	                        Flexível
Escalabilidade	                        Vertical	                    Horizontal
Performance	                Melhor em consultas complexas	    Melhor em grandes volumes de leitura/escrita
Consistência	                        Alta (ACID)	                    Pode priorizar disponibilidade (BASE)
Uso Típico	                ERP, CRM, transações bancárias	    Big Data, IoT, redes sociais
```
# ==================

# ////////////// ////////////  ENGLISH ///////////// ///////////////////// ///////////////////// ////////////// //////
# SQL
## Concept
    - Organized in a tabular structure (tables / relationships)
    - Tables related to each other through foreign and primary keys
    
    * Relational Integrity: Rules ensure data integrity
        - Primary key: Ensures each record is unique in the table
        - Foreign key: Relates tables and maintains referential consistency between them
## ACID
    - Atomicity: The transaction is fully completed or not performed at all
    - Consistency: The database remains in a valid state after a transaction
    - Isolation: Parallel transactions do not interfere with each other
    - Durability: Data persists even after a failure
## Joins
### Summary
    JOIN	Behavior
    INNER	Only matching records between tables.
    LEFT	All records from the left table, with NULL for non-matching rows.
    RIGHT	All records from the right table, with NULL for non-matching rows.
    FULL	All records from both tables, filling with NULL where necessary.
    CROSS	Cartesian product of both tables.
    SELF	Join between a table and itself.
```text
EXEMPLO INNER
SELECT clientes.nome, pedidos.id, pedidos.valor
FROM clientes
INNER JOIN pedidos ON clientes.id = pedidos.cliente_id;

tabela cliente tem id e nome
tabela pedidos tem id e valor
Nova tabela nome,id e valor
```
    - LEFT: All records from the left table and matching records from the right table
    - Non-matching rows from the right table will return as NULL

    * Note: For Right Join, the logic is the same but with the right table
```text
EXEMPLO LEFT
SELECT clientes.nome, pedidos.id, pedidos.valor
FROM clientes
INNER JOIN pedidos ON clientes.id = pedidos.cliente_id;

tabela cliente tem id e nome
id , nome
1     Joao
2     Maria

tabela pedidos tem id e valor
id , cliente.id valor
101    1         100
102    1         200

Nova tabela nome,id e valor
nome,id valor
joao  101  100
joao  102  200
maria  null null
```

    - FULL JOIN: Combines all records from all tables, NULL where no match exists

```text
EXEMPLO FULL
SELECT clientes.nome, pedidos.id, pedidos.valor
FROM clientes
INNER JOIN pedidos ON clientes.id = pedidos.cliente_id;

tabela cliente tem id e nome
id , nome
1     Joao
2     Maria

tabela pedidos tem id e valor
id , cliente.id valor
101    1         100
102    2         200

Nova tabela nome,id e valor
nome,id valor
joao  101  100
maria  null  null
null  102   200
```
## Querys
```text - BUSCA BÁSICA
SELECT * FROM clients; all data from the table
SELECT name, email FROM clients; Specific columns
SELECT name, email FROM clients WHERE city = 'São Paulo'; Filter by specific data
SELECT name, email FROM clients ORDER BY name ASC; Sorting search -- ASC for ascending, DESC for descending
SELECT name, email FROM clients LIMIT 5; Limit the result -- Shows only the first 5 records
```
```text - CONDICIONAL
SELECT * FROM orders
WHERE value > 500 AND status = 'Shipped';

SELECT * FROM orders
WHERE status = 'Pending' OR value > 1000;

SELECT * FROM clients
WHERE city IN ('São Paulo', 'Rio de Janeiro', 'Belo Horizonte');

SELECT * FROM orders
WHERE date BETWEEN '2025-01-01' AND '2025-01-31';

SELECT * FROM clients
WHERE name LIKE 'Jo%'; -- Names that start with 'Jo'
```
```text FUNÇÔES AGREGADA
SELECT COUNT(*) AS total_clients FROM clients; counts the records

SELECT SUM(value) AS total_sales FROM orders; sums the values of the records

SELECT AVG(value) AS avg_sales FROM orders; averages the values of the records

SELECT MAX(value) AS max_order, MIN(value) AS min_order FROM orders; Highest and Lowest values 
```
```text AGRUPAMENTO
SELECT city, COUNT(*) AS total_clients
FROM clients GROUP BY city; Grouping data

SELECT city, COUNT(*) AS total_clients
FROM clients GROUP BY city
HAVING COUNT(*) > 10; -- Shows only cities with more than 10 clients | Filters grouped results
```
# NoSQL
    - Does not use tables, rows, and columns as its primary structure
      - Data is stored as documents, key-value pairs, graphs, or wide-columns
    
      * Characteristics of NoSQL
      - Flexibility: Can store structured, semi-structured, and unstructured data
      - Horizontal Scalability: Add more servers to handle increased data
      - High Performance: Optimized for fast read and write operations at scale

## Types of NoSQL
    - Document-Oriented
    * Data in JSON, BSON, or XML format
    * Allows different fields and structures for flexibility
    * Examples: MongoDB, Couchbase, Amazon DocumentDB

    - Key-Value
    * Data in key-value pairs, where the key is unique and used to access the value
    * Fast and simple, ideal for caching and simple storage
    * Examples: Redis, Amazon DynamoDB, Memcached
```text
chave: cliente:1
valor: {"nome": "Maria", "cidade": "São Paulo"}
```
    - Graph Databases
        * Data represented as nodes and edges, showing entities and their relationships
        * Useful for social networks, recommendation systems, and network analysis
        * Examples: Neo4j, ArangoDB, Amazon Neptune
## Exemplos
```text -> APLICAÇÂO 
Banco               | Type           | Use Case
MongoDB             | Document       | Web applications, flexible data, logs
Redis               | Key-Value      | Caching, queues, sessions
Neo4j               | Graph          | Social networks, recommendation systems
Apache Cassandra    | Wide-Columns   | Data warehouses, IoT, large data volumes
DynamoDB            | Key-Value/Doc  | Highly scalable systems
HBase               | Wide-Columns   | Distributed large data volumes
```
## SQL vs NOSQL
```text
Aspect            |    Relational                 |  Non-Relational
Data Model        |    Structured (tables, rows)  |  Flexible (documents, graphs, etc.)
Schema            |    Strict                     |  Flexible
Scalability       |    Vertical                   |  Horizontal
Performance       |    Better for complex queries |  Better for high-volume reads/writes
Consistency       |    High (ACID)                | Can prioritize availability (BASE)
Typical Use Cases |    ERP, CRM, transactions     |  Big Data, IoT, social networks
```
# **************************

#  WEB
## REST
    - An architectural style that defines a set of constraints for web services
    Principles:
        - Client-Server: The client makes requests, and the server processes and responds
        - Stateless: The server does not store the client state between requests
        - Uniform Interface: REST uses standard HTTP methods to interact with resources
### REST-Full
    - Implements REST principles, based on HTTP, and uses HTTP methods (GET, POST, DELETE, PUT)
    - Supports JSON or XML formats
    
    * Advantages
        - Simplicity: Easy to understand and implement, as it uses familiar HTTP conventions.
        - Interoperability: Can be used by any client that supports HTTP, such as browsers, mobile apps, etc.
        - Independence: Client and server can evolve independently.
# *************************