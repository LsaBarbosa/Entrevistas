# CLOUD
## AWS S3
    - Serviço de armazenamento de objeto escalável, serve para armazenar e recuperar grandes quantidades de dados
    - Escalabilidade Automatica com base na demanda, não há necessidade de provisionar
### Conceito
    - Dados em Objetos armazenados dentro dos buckets
        - Objeto é um dado(arquivo), metadado(infromação sobre arquivo), e uma chave única 
    
    - Buckets: Containers para armazenar objetos. Deve ter um nome único globalmente
    - Disponível e Durável

### Classes de Armazenamento
    - S3 Standard: Alta durabilidade, baixa latencia, ideal para uso frequente
    - S3 Intelligent-Tiering: Move automaticamente objetos entre classes de armazenamento para otimizar custos
    - S3 Standard-IA (Infrequent Access): Ideal para dados acessados esporadicamente.
    - S3 Glacier: Para arquivamento de longo prazo com custo reduzido.
    - S3 Glacier Deep Archive: Ainda mais barato, mas com maior tempo de recuperação.
## AWS RDS
### Conceito
    - Supote a vários motores de banco de dados 
    - Totalmente gerenciavel, alta disponibilidade, replicaçãao
    - Escalabilidade vertical (maior poder computacional) e horizontal(réplicas de leitura)
## DynamoDB
### Conceito
    - Modelo Dados Flexível
        - Baseado em tabelas, mas sem um esquema fixo
        - Cada Item é identificado por uma chave primáriae pode conter atributos diferentes
    - Baixa Latência: resposta rápidas mesmo sob alta demanda
    
    - Modelos de Consistência:
        - Eventual: Leitura pode não refletir imediatamente a última gravação, mas tem maior perfomance
        - Conssitencia Forte: Garante que a leitura reflita o último estado dos dados
### Componentes
    - Tabelas: Estrutura principal onde os dados são armazenados; Sem limite de tamanho
    
    - Chave-Partição: Define como os dados são organizados e acessados
        - Uma única chave que deermina onde os dados são armazenados no sistemas 
    - Chave-Composta: Combina chave de partição e chave de ordenação
        - Ex: userId(partition Key) + createdAt (Sort key) para armazenar mensagens ordenadas no tempo

    - Índice: Melhoram a performance de consultas
        - indice secundario Local: usa a mesma chave de partição da tabela principal, permite chave de ordenação
        - indice secundario Global: permite consultas em difeentes chaves de partição e ordenação
# ==================

# ENGLISH
# CLOUD
## AWS S3
    - Scalable object storage service designed for storing and retrieving large amounts of data
    - Automatically scales based on demand; no need for provisioning
### Concept
    - Data is stored as objects inside buckets
        - An object consists of data (file), metadata (information about the file), and a unique key
    
    - Buckets: Containers for storing objects. Each bucket must have a globally unique name
    - Highly available and durable
### Storage Classes
    - S3 Standard: High durability, low latency, ideal for frequent use
    - S3 Intelligent-Tiering: Automatically moves objects between storage classes to optimize costs
    - S3 Standard-IA (Infrequent Access): Ideal for data accessed occasionally
    - S3 Glacier: For long-term archival with reduced cost
    - S3 Glacier Deep Archive: Even cheaper but with longer retrieval times
## AWS RDS
### Concept
    - Supports multiple database engines
    - Fully managed with high availability and replication
    - Scales vertically (more computational power) and horizontally (read replicas)
## DynamoDB
### Concept
    - Flexible Data Model
        - Table-based but schema-less
        - Each item is identified by a primary key and can have varying attributes
    - Low Latency: Fast responses even under high demand
    
    - Consistency Models:
        - Eventual: Reads may not immediately reflect the latest writes but offer better performance
        - Strong: Ensures reads reflect the latest data state
### Components
    - Tables: The primary structure where data is stored; no size limit
    
    - Partition Key: Defines how data is organized and accessed
        - A single key determines where data is stored in the system
    - Composite Key: Combines partition key and sort key
        - E.g., userId (partition key) + createdAt (sort key) to store messages ordered by time

    - Index: Improves query performance
        - Local Secondary Index: Uses the same partition key as the main table but allows different sort keys
        - Global Secondary Index: Enables queries on different partition and sort keys
# **************************