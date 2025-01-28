## Spring Cloud
### CORE
    - Ajuda na criação de aplicações Cloud-Native e distribuidas (Arquitetura de Microserviços)
    - Prove Soluções para ambientes de microserviços:
        - Config Centralizada, Service Discovery, Circuit brakers, roteamento, observabilidade
### Service Descovery
    - Microserviços se comunicam sem uso de ip/host fixos
    - Serviço A pode descobrir o endereço B em tempo de execução
    - facilita a escalabilidadfe e verçoes dinamicas de serviços
        
        * EUREKA: Um registro em que cada serviço se registra e descobre os outros
        
        * CONSUL e ZOOKEEPER: Solução alternativa suportadas pelo Spring cloud
### Roteamentoo e GATEWAY
    - Roteamento com base em URLs ou Cabeçalhos
    - Filtros para autenticação, logs, limitação de taxa (rate-limiting)
    - Load-Balance( integrando com service deiscovery )
### Circuit Breaker
    - Em arquiteturas distribuida, um serviço que depende do outro pode falhar, para lidar com isso
    
    * Spring cloud circuit breaker: abstrai a funcionalidade de circuit braker
        - e Adoçãod e bibliotecas como Resilience4J

    * Fallbacks : caso o serviço remoto não responda, definindo um comportamento de contigência
### Cloud Stream Mensageria
    - Integração assincrona

    * Spring cloud Stream: Abstrai sistemas de mensagens ( RabbitMQ, Kafka) usando binders
        - Anota metodo com @StreamListener e o Spring configura filas, topicos etc

    * Facilita event-driven achitecture:
        - Em que cada serviço envia/consome eventos de um barramento de mensageria


web client, rest template: inserir em mensageria tbm
