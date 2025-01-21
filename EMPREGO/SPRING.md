# SPRING FRAMEWORK
## Core
### Benefícios
    - Desacoplamento: Cada classe foca em sua lógica, sem gerenciar e criar dependencia
    - Testabilidade: Com injeção de dependencias, fica mais facíl mockar
### Inversão de Controle
        * Padrão de projeto que delega a instância e o gerenciamento de objetos para um container ou framework 
            - Cria instancia dos objetos (chamados Beans)
            - Injeta dependencia entre eles ( via construtor, Setter, Autowired)
            - Gerencia o ciclo de vida desses objetos
### Beans
            - É um objeto gerenciado pelo container do Spring
            - Qualquer class pode ser Bean se declarada com anotações (Component, Service, Repository, Controller
#### Ciclo de vida
    - Localiza a definição do bean
    - Instancia o bean ( chamando construtor)
    - Injeta as dependencias 
    - Ao encerrar o contexto métodos de destruição podem ser chamados
#### Escopos @(Scope)
    - Singleton: Cria apenas uma instância do bean para todo contexto Spring ( é o padrão )
    - Prototype: Uma nova instancia sempre que o bean é requisitado ao container
    - Requeste: Uma nova instancia  por requisição HTTP (uso em apps web)
    - Session: Uma instancia por sessão HTTP
### AOP
    - Programação Orientada a aspectos
        * Modulariza funcionalidades transversais em aplicações java

        * Separa funcionalidade trasnversal da logica principal
            podem ser tratados de forma isolada em vez de ser repetidos em varias partes do código
            - Loggin, autenticação, Tratamento de exception
#### Vantagem
    - Modularidade: facilita a separção de responsabilidade
    - Reutilização: Evita a duplicação do código
    - Manutenção: facilita a manutenção e compreensão do código
## MVC
    - Model: representa os dados ou a lógica de negócio da aplicação.
    - View: é a camada de apresentação (por exemplo, páginas HTML ou respostas JSON).
    - Controller: recebe as requisições, processa a lógica (chamando o Model) e retorna a View apropriada.
    - Simplificação de criação de aplicação WEB usando model view controller
    - Uso de anotações como RestController, Controller, RequestMApping

    * Data Binding
        - Faz mapeamento automático dos campos para um objeto Java
        - Elimina o parse manual

    * Fluxo no MVC
        - Cliente faz requisição que é interpretada pelo Dispatcher Servlet
        - Dispatcher delega a requisição para o controller, com base no mapeamento de rotas
        - Controller chama serviços, repositories, lógicas etc
        - Controller retorna a view ( ou objeto se for um RestController)
        - View Resolver resolve qual arquivo deve ser renderizado
        - Dispatch server junta os dados do model com template e retorna a resposta ao cliente
## Spring Data
    - Contem subprojetos para acesso facilitado a banco de dados relacional e nao relacional
        como Spring Data Jpa, Spring Data Mongo
### JPA
#### Vantagem
    - Eliminar cod repetitivo de CRUD
    - Permitir a criação de Derived Queries, Consultas personalizadas
#### Core
    - Cria repositório declarando interfaces sem escrever SQL ou HQL diretamente (mas é possível)
    
    * Query Methods (Derived Methods)
        - Métodos que os sprging deriva com base no nome dos métodos evitando uso de SQL
            - findLastName(String lastName) equivale a SELECT c FROM Customer c WHERE c.lastName = ?

    * Transaction
        - Garante a consistencia de dados, em caso de exceção o Spring faz o rollback automático
    
    * Paggination e Sorting
        - Fornece metodos para paginaçao e sortting
#### Consultas @Query)
        - JPQL: linguagem de consulta orientada a objeto, opera sobre entidade e seus campos
''
@Query("SELECT c FROM Customer c WHERE c.age > :minAge")
List<Customer> findAllOlderThan(@Param("minAge") int minAge);

        - Nativa: usa SQL nativo
```text

@Query(
value = "SELECT * FROM customers WHERE age > :minAge",
nativeQuery = true
)
List<Customer> findAllOlderThanNative(@Param("minAge") int minAge);
```

        - Named Query: Consultas pre-definidas(JPQL ou nativo) que recebem um nomee ficam associadas à entidade
```text

@Entity
@NamedQueries({
@NamedQuery(
name = "Customer.findByLastName",
query = "SELECT c FROM Customer c WHERE c.lastName = :lastName"
),
@NamedQuery(
name = "Customer.findByAgeGreaterThan",
query = "SELECT c FROM Customer c WHERE c.age > :age"
)
})
public class Customer {
// ...
}
                       ==> chamadando a named query <==

                        @Query(nativeQuery = false, name = "Customer.findByLastName")
                        List<Customer> findByLastName(@Param("lastName") String lastName);
```
### Hibernsate
    - Mapeamento de onejto Relacional (ORM), abstrai operações de persistencia 
        ao converter classes e relacionamentos em tabelas e colunas e vice versa

    - JPA é uma especificação que define como o ORM deve funcionar
        o Hibernate é uma implementação dessa especificação, fornecendo o motor que realiza a persistencia
## Spring Boot
    - Um Wrapper que facilita a configuração, empacotamento e inicialização de app springs
    - Carrega de modo automatico modulos como TomCat (Embbeded Server), MVc conforme dependencias no classPath
    - Centraliza configs no arquivos Application Properties ou yaml
    - Suporte a Configurações de Profiles: dev, test, prod  (spring.profiles.active=dev)
### Starter
        - Artefatos que reunem num pacote biblioteca necessária para determinada funcionalidade
        - STARTER-WEB: inclui o mvc, TomCat, validaçao
        - STARTER-DATA-JPA: Data JPA, Hibernate e Transações
        - STARTER-SECURITY: Spring Security e dependencias
        - STARTER-TEST: Junit, Mockito, Spring Test
### Actuator
        - Expões diversos endpints para monitoramento e gestão da aplicação
        - Auxilia na observabilidade da aplicação, especialmente em produção
### Vantagem
    - Produtividade: menos Config manual e mais convenções
    - Aplicações StandAlone: Tomcat/Jetty embutido, facilitando execução e deploy
    - Auto Config: Confgura componentes de forma automatica conforme dependencias no classPath
    - Integração com outras partes do Spring: Spring MVC, DATA, SECURITY
## Spring Security
    - Criado para cuida de autenticação e e autorização
    - Permite configuração de regras de acesso, integração com OAuth2, Ldap, JWT
    - Permite Proteção tanto em URL quanto por métodos ( metodos de autorização)

    * Security Filter Chain:
        - Configura como as requisições devem ser protegidas
        - Quais Endpoints serão protegidos e quis serão públicos, quais precisam de autenticação

    * User Deatails: Responsável por carregar detalhes de usuários 
        - Retorna um objeto userDetails contendo infromações do user

    * PasswordEcoder: Responsável por Codificar e comparar as senhas (BCrypt, PBKDF2 etc.)

    * Authentication: Interface que descreve a identidade do user após o login 
    * Authorization: Feita checando se o user autenticado tem permissão para o recurso
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
# ==================

# ENGLISH
# SPRING FRAMEWORK
## Core
### Benefits
    - Decoupling: Each class focuses on its logic without managing or creating dependencies
    - Testability: Dependency injection makes mocking easier
### Inversion of Control
        * Design pattern that delegates the instantiation and management of objects to a container or framework 
            - Creates instances of objects (called Beans)
            - Injects dependencies between them (via Constructor, Setter, Autowired)
            - Manages the lifecycle of these objects
### Beans
            - A Bean is an object managed by the Spring container
            - Any class can be a Bean if declared with annotations (Component, Service, Repository, Controller)
#### Lifecycle
    - Locates the bean definition
    - Instantiates the bean (calling the constructor)
    - Injects dependencies 
    - On context shutdown, destruction methods can be called
#### Scopes @(Scope)
    - Singleton: Creates only one instance of the bean for the entire Spring context (default scope)
    - Prototype: Creates a new instance every time the bean is requested from the container
    - Request: Creates a new instance per HTTP request (used in web applications)
    - Session: Creates one instance per HTTP session
### AOP (Aspect-Oriented Programming)
    - Programming paradigm that modularizes cross-cutting concerns in Java applications

    - Separates cross-cutting functionality from the main logic
        * These functionalities can be handled in isolation instead of being repeated across multiple parts of the code
        * Examples: Logging, Authentication, Exception Handling

#### Advantages
    - Modularization: Simplifies the separation of responsibilities
    - Reusability: Avoids code duplication
    - Maintenance: Enhances code maintainability and readability
## MVC
    - Model: Represents the data or business logic of the application
    - View: The presentation layer (e.g., HTML pages or JSON responses)
    - Controller: Handles requests, processes the logic (calling the Model), and returns the appropriate View
    - Simplifies the creation of web applications using the Model-View-Controller pattern
    - Uses annotations such as RestController, Controller, RequestMapping

    * Data Binding
        - Automatically maps fields to a Java object
        - Eliminates manual parsing

    * MVC Flow
        - Client sends a request interpreted by the Dispatcher Servlet
        - Dispatcher delegates the request to the Controller based on route mapping
        - Controller calls services, repositories, logic, etc.
        - Controller returns the View (or object if it's a RestController)
        - View Resolver determines which file should be rendered
        - Dispatch Servlet combines the Model data with the template and returns the response to the client
## Spring Data
    - Contains subprojects for simplified access to relational and non-relational databases
        such as Spring Data JPA, Spring Data Mongo
### JPA
#### Advantages
    - Eliminates repetitive CRUD code
    - Enables the creation of Derived Queries and custom queries
#### Core
    - Creates repositories by declaring interfaces without writing SQL or HQL directly (though possible)
    
    * Query Methods (Derived Methods)
        - Methods derived by Spring based on method names, avoiding SQL usage
            - findLastName(String lastName) is equivalent to SELECT c FROM Customer c WHERE c.lastName = ?

    * Transactions
        - Ensures data consistency; in case of exceptions, Spring performs automatic rollback
    
    * Pagination and Sorting
        - Provides methods for pagination and sorting
#### Queries (@Query)
```text
        - JPQL: Object-oriented query language, operates on entities and their fields
        
        @Query("SELECT c FROM Customer c WHERE c.age > :minAge")
        List<Customer> findAllOlderThan(@Param("minAge") int minAge);
```
```text
        - Nativa: usa SQL nativo
        
        @Query(
        value = "SELECT * FROM customers WHERE age > :minAge",
        nativeQuery = true
        )
        List<Customer> findAllOlderThanNative(@Param("minAge") int minAge);
```
```text
        - Named Query: Consultas pre-definidas(JPQL ou nativo) que recebem um nomee ficam associadas à entidade
        
        @Entity
        @NamedQueries({
        @NamedQuery(
        name = "Customer.findByLastName",
        query = "SELECT c FROM Customer c WHERE c.lastName = :lastName"
        ),
        @NamedQuery(
        name = "Customer.findByAgeGreaterThan",
        query = "SELECT c FROM Customer c WHERE c.age > :age"
        )
        })
        public class Customer {
        // ...
        }
                       ==> chamadando a named query <==

                        @Query(nativeQuery = false, name = "Customer.findByLastName")
                        List<Customer> findByLastName(@Param("lastName") String lastName);
```
### Hibernate
    - Object-Relational Mapping (ORM) framework that abstracts persistence operations
        by converting classes and relationships into tables and columns and vice versa

    - JPA is a specification that defines how ORM should work
        Hibernate is an implementation of this specification, providing the engine for persistence
## Spring Boot
    - A wrapper that simplifies the configuration, packaging, and initialization of Spring applications
    - Automatically loads modules like Tomcat (Embedded Server), MVC, based on dependencies in the classpath
    - Centralizes configurations in Application Properties or YAML files
    - Supports Profile Configurations: dev, test, prod (spring.profiles.active=dev)
### Starter
        - Artifacts that group the necessary libraries for specific functionalities
        - STARTER-WEB: Includes MVC, Tomcat, validation
        - STARTER-DATA-JPA: Includes Data JPA, Hibernate, and transaction management
        - STARTER-SECURITY: Spring Security and dependencies
        - STARTER-TEST: Includes JUnit, Mockito, Spring Test
### Actuator
        - Exposes several endpoints for application monitoring and management
        - Aids in application observability, especially in production
### Advantages
    - Productivity: Less manual configuration and more conventions
    - Standalone Applications: Embedded Tomcat/Jetty, simplifying execution and deployment
    - Auto Configuration: Automatically configures components based on classpath dependencies
    - Integration with Other Spring Modules: Spring MVC, DATA, SECURITY
## Spring Security
    - Built to handle authentication and authorization
    - Allows configuring access rules, integration with OAuth2, LDAP, JWT
    - Protects both at the URL level and by method (authorization methods)

    * Security Filter Chain:
        - Configures how requests should be protected
        - Defines which endpoints are protected, public, or require authentication

    * User Details: Responsible for loading user details
        - Returns a userDetails object containing user information

    * PasswordEncoder: Responsible for encoding and comparing passwords (e.g., BCrypt, PBKDF2)

    * Authentication: Interface that describes the user's identity after login
    * Authorization: Checks if the authenticated user has permission for the resource
## Spring Cloud
### Core
    - Assists in building cloud-native and distributed applications (Microservices Architecture)
    - Provides solutions for microservices environments:
        - Centralized Configuration, Service Discovery, Circuit Breakers, Routing, Observability
### Service Discovery
    - Microservices communicate without using fixed IP/host
    - Service A can discover Service B's address at runtime
    - Facilitates scalability and dynamic service versions
        
        * EUREKA: A registry where each service registers and discovers others
        
        * CONSUL and ZOOKEEPER: Alternative solutions supported by Spring Cloud
### Routing and Gateway
    - Routing based on URLs or Headers
    - Filters for authentication, logging, rate-limiting
    - Load balancing (integrated with service discovery)
### Circuit Breaker
    - In distributed architectures, a service that depends on another can fail. To handle this:
    
    * Spring Cloud Circuit Breaker: Abstracts circuit breaker functionality
        - Adopts libraries like Resilience4J

    * Fallbacks: Defines fallback behavior if the remote service does not respond
### Cloud Stream Messaging
    - Asynchronous Integration

    * Spring Cloud Stream: Abstracts messaging systems (RabbitMQ, Kafka) using binders
        - Annotate methods with @StreamListener, and Spring configures queues, topics, etc.

    * Facilitates Event-Driven Architecture:
        - Where each service sends/consumes events from a messaging bus
# **************************