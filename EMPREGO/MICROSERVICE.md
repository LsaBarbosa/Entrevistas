# MICEROSERVICE
## Conceitos
    - Independência: Serviços independentes e automonos, desenvolvidos,testado e implantado e escalado de forma isolada
    - Baixo Acoplamento: Projetados para minimizar as dependencias entre si
    - Comunicação: Usando Apis Rest, gRPC, ou Mensageria(RabbitMQ, Kafka)
    - Tecnologia Heterogenica: Possibilidade de serviços distintos teram tecnologias distintas
## Vantagem
    - Escalabilidade: Serviços individuais podem ser escalados independentemente com base na demanda
    - Manutenibilidade: Alterações num serviço não afetam o resto do sistema
    - Desenvolvimento em Paralelo: Equipes podem trabalhar simultaneamente em diferentes microservicos
    - Ciclo de deploy independente: Atualização e correção de um serviço nao exigem o redeploy de toda aplicação
## Componentes MS
    - Seviços Autonomos: Cada microserviço independente e focado numa responsabilidade
    - APIs: Interface para interação entre serviços ou consumidores externos
    - BD por serviço: Serviços gerenciam seus propios daods para evitar dependencia
    - Mensageria/Events: Comunicação assincrona entre serviços usando mensagens ou eventos
    - API Gateway: ponto de entrada unificado para consumidores, esponsavel por rotear requisição para serviços corretos
## Comunicação
    - Síncrona: Baseada em requisições diretas, Rest ou gRPC
        * Vantagem: simples implementação, suportadas por frameworks
        * Desvantagem: Latencia aumenta com numero de serviços, dependencia imediata da disponibilidade do serviço

    - Assíncrona: Mensageria/eventos(RabbitMq, Kafka, SNS e SQS)
        * Vantagem: Reduz acoplamento entre serviços, tolerancia a falhas e alta escalabilidade
        * Desvantagem: Requer infraestrutura de msg, Lida com consistência eventual
## Ferramentas
    - Orquestração: Kubbernets orquestração de containers para deploy e escalabilidade
                    Docker para isolamento de serviços
    
    - Monitoramento: Promrtheus + Grafana monitoramentos e Logs
                     Jaeger / Zipkin Tracing distribuidos
                     ELK Stack Logs centralizados
    - API Gatewai: Spring cloud Gateway, Kong API, NGINX
# ==================
# MENSAGERIA
## Vantagens
    - Desacoplamento: Produtor/ Consumidor não precisam estar ativos, nem conhecer detalhes um do outro
    - Escalabilidade: Pode adicionar  mais instancia de consumidores pra lidar com aumento de volume de msg
    - Resiliencia: Se o consumidor cair, as msg ficam na fila / topico até que outro consumidor processe
    - Assincronicidade: Produtor nao precisa esperr a operação de processamento temrinar, melhor performance evita bloqueio
    - Comunicação Multiplos Destinatários: Com pub/sub a mesma msg pode disparar ações em varios serviços diferentes

    * Quando Usar
        - Em processos assíncronos ou que precisam ser executados em segundo plano (não precisa de resposta imediata)
        - Quando deseja desaclopar os serviços, evitando que um serviço dependa da disponiilidade do outro
        - Fluxo de alto volume de dados, logs, streaming , telemetria
## Conceitos
### Idepotencia 
    - Capacidade de um sistema processar a mesma mensagem múltiplas vezes 
        sem causar efeitos colaterais ou resultados indesejados
### Produtor
    - Serviço que envia msg ao sistema de mensageria
### Consumidor 
    - Serviço que consome a msg do sistema de mensageria
### Fila: 
    - Estrutura em que as msg são enfileiradas pra um processamento
### Tópico: 
    - Publicação e assinatura (pub;sub) a msg pode ser replicada para multiplis consumidores cadastrados no tóp
### Broker: 
    - Intermediário que gerencia o fluxo de msg, armazenando e encaminhando para os consumidores
        * Pode oferecer:
            - Durabilidade: grava msg m disco
            - Ordem: Msg processada em sequência
            - Confirmação: Recebimento da Msg

        * Exemplos: Rabbit, Kafka, Amazon SQS, Google pub/Sub
### Mensagem
    - Pode ser em texto (Json), ou formatos específicos (AVRO, PROTOBUF)
#### Troca de MSG
    - RabbitMQ: uso de EXCHANGES (Direct, Topic, Fanout) que determina como uma msg é roteada para filas
    - Kafka: Partições em tópicos que segmentam carga entre o consumidores
## Arquiteturas
### Ponto Ponto QUEUE
    - Modelo: há uma fila entre Produtores e Consumidores
    - Entrega: Cada msg é consumida por apenas um consumidor, o primeiro que estiver disponível para processar
    - Aplicação: Cenários e trefas assincronas, cada msg representa um job ou uma task ser executada por um worker
    - Exemplo: RabbitMQ, ActiveMq, AWS SQS
### Pub/Sub
    - Modelo: Há um tópico ao qual os produtores publicam as mensagens e consumidores se inscrevem no tópico
    - Entrega: A mesma mensagem pode ser entregue a vários consumidores, cada um inscrito no tópico 
    - Aplicação: Cenários em que uma mensagem precisa disparar ações em multiplos serviços (enviar notificações, atualizar cache, gerar relatórios)
    - Exemplo: Kafka, Google Pub/Sub, RabbitMQ com Exchange do tipo fanout
## Topologia
### Point-to-Point
    - Um ou mais produtores colocam as msg na fila
    - Um ou mais consumidores competem para processar as msg 
    - Cada um sendo processado por apenas um consumidor
### Pub/Sub
    - Um produtor pulica num tópico
    - Todos os consumidores que se inscreverem no tópico recebem a mesma msg
    - util para broadcasting
### Request/Replay
    - Consumidor ao receber a msg envia uma resposta ao produtor por outra fila ou tópico
    - É assincrono  mas permite um fluxo de requisição e resposta desaclopado
## Tecnologias
### RabbitMQ
    - Usa AMQP, Focada em filas, exchanges (Direct, Topic, Fanout) roteamento de msg
    - utilizada em Microserviços para processamentos de tarefas assíncronas
### Apache Kafka
    - Focada em Streaming de dados Pu/Sub de alta vazão
    - Persistencia em disco distribuida (cluster de brokers), alta escalabilidade e patições em tópicos
    - Usada em grande volumes de daods , integração em tempo real (event Streaming) e analytics
### Amazon SQS
    - Serviços gerenciados pela AWS para filas SQS, e pub/sub SNS
    - Não precisa operar broker, paga por uso
# ==================

# ENGLISH
# MICROSERVICES
## Concepts
    - Independence: Services are independent and autonomous, developed, tested, deployed, and scaled in isolation
    - Low Coupling: Designed to minimize dependencies between services
    - Communication: Uses APIs (REST, gRPC) or messaging (RabbitMQ, Kafka)
    - Heterogeneous Technology: Different services can use distinct technologies
## Advantages
    - Scalability: Individual services can be scaled independently based on demand
    - Maintainability: Changes in one service do not affect the rest of the system
    - Parallel Development: Teams can work simultaneously on different microservices
    - Independent Deployment Cycle: Updating or fixing one service does not require redeploying the entire application
## MS Components
    - Autonomous Services: Each microservice is independent and focused on a specific responsibility
    - APIs: Interface for interaction between services or external consumers
    - Database per Service: Each service manages its own data to avoid dependencies
    - Messaging/Events: Asynchronous communication between services using messages or events
    - API Gateway: Unified entry point for consumers, responsible for routing requests to the correct services
## Communication
    - Synchronous: Based on direct requests, e.g., REST or gRPC
        * Advantage: Simple implementation, supported by frameworks
        * Disadvantage: Latency increases with the number of services; immediate dependency on service availability

    - Asynchronous: Messaging/events (RabbitMQ, Kafka, SNS, and SQS)
        * Advantage: Reduces coupling between services, fault tolerance, and high scalability
        * Disadvantage: Requires messaging infrastructure, deals with eventual consistency
## Tools
    - Orchestration: Kubernetes for container orchestration, deployment, and scalability
                     Docker for service isolation
    
    - Monitoring: Prometheus + Grafana for monitoring and logs
                  Jaeger / Zipkin for distributed tracing
                  ELK Stack for centralized logs
    - API Gateway: Spring Cloud Gateway, Kong API, NGINX
# **************************
# MESSAGING
## Advantages
    - Decoupling: Producers/Consumers do not need to be active or know details about each other
    - Scalability: Additional consumer instances can handle increased message volumes
    - Resilience: If a consumer fails, messages remain in the queue/topic until another consumer processes them
    - Asynchronicity: Producers do not wait for processing to complete, improving performance and avoiding blocking
    - Multi-Recipient Communication: With pub/sub, the same message can trigger actions in multiple services

    * When to Use:
        - For asynchronous processes or tasks executed in the background (no immediate response required)
        - To decouple services, avoiding dependency on each other's availability
        - For high-volume data flows, logs, streaming, and telemetry
## Concepts
### Idempotency
    - Ability to process the same message multiple times without causing unintended side effects
### Producer
    - Service that sends messages to the messaging system
### Consumer
    - Service that consumes messages from the messaging system
### Queue
    - Structure where messages are enqueued for processing
### Topic
    - Publish/Subscribe (pub/sub) structure; messages can be replicated to multiple registered consumers
### Broker
    - Intermediary that manages message flow, storing and forwarding them to consumers
        
        * Can Offer:
            - Durability: Stores messages on disk
            - Order: Ensures messages are processed sequentially
            - Acknowledgment: Confirms message receipt

        * Examples: RabbitMQ, Kafka, Amazon SQS, Google Pub/Sub
### Message
    - Can be in text format (JSON) or specific formats (AVRO, PROTOBUF)
#### Message Exchange
    - RabbitMQ: Uses EXCHANGES (Direct, Topic, Fanout) to route messages to queues
    - Kafka: Uses partitions in topics to distribute load among consumers
## Architectures
### Point-to-Point (Queue)
    - Model: A queue exists between producers and consumers
    - Delivery: Each message is consumed by only one consumer, whichever is available first
    - Application: Asynchronous tasks where each message represents a job or task processed by a worker
    - Example: RabbitMQ, ActiveMQ, AWS SQS
### Publish/Subscribe (Pub/Sub)
    - Model: A topic where producers publish messages and consumers subscribe to the topic
    - Delivery: The same message can be delivered to multiple consumers, each subscribed to the topic
    - Application: Scenarios where a message triggers actions across multiple services (e.g., notifications, cache updates, reports)
    - Example: Kafka, Google Pub/Sub, RabbitMQ with Fanout Exchange
## Topologies
### Point-to-Point
    - One or more producers place messages in the queue
    - One or more consumers compete to process the messages
    - Each message is processed by only one consume
### Publish/Subscribe
    - A producer publishes to a topic
    - All consumers subscribed to the topic receive the same message
    - Useful for broadcasting
### Request/Reply
    - Consumers, upon receiving a message, send a response to the producer via another queue or topic
    - Asynchronous but enables a decoupled request/response flow
## Technologies
### RabbitMQ
    - Uses AMQP, focused on queues and exchanges (Direct, Topic, Fanout) for message routing
    - Commonly used in microservices for asynchronous task processing
### Apache Kafka
    - Focused on high-throughput Pub/Sub data streaming
    - Distributed disk persistence (broker clusters), high scalability, and topic partitions
    - Used for high data volumes, real-time integration (event streaming), and analytics
### Amazon SQS
    - AWS-managed service for SQS queues and SNS pub/sub
    - No need to operate a broker; pay-per-use model
# **************************