# Experiences
## Itaú
### Itaú HR
    - I started my career working at Itaú, which is one of the main players in the financial sector.
        There, I had my first contact with Clean Architecture and was able to put into practice programming principles
        and best practices such as Clean Code and the SOLID principles.

    - Additionally, I developed, monitored, maintained, and improved APIs using Java, Spring Framework,
        as well as testing tools like JUnit and Mockito.
### Itaú Tech
    - Implemented features in APIs using Java and Spring, adhering to best programming practices:
        * Such as meaningful names, short functions with specific goals.

    - Also adhered to the Clean Architecture rules, separating business logic from the rest of the application:
        * Using interfaces and modular separation.

    - Performed application maintenance and monitored the production environment:
        * Using Splunk to check logs, Grafana and Kubernetes to verify the application's status.

    - Created and updated documentation in Confluence, and mapped some APIs in OpenAPI.
    - Databases: PostgreSQL, SQLServer, and Redis for caching.

## B2B
    - After this experience, I worked with contracts in the B2B model.
    - Developed some commercial pages for local companies using Angular, React, and TypeScript.
        With this, I greatly improved my communication and organization skills.
        However, two projects were the most relevant to me.

### Benkyo
#### Benkyo HR
    - The first was a school system that manages the entire lifecycle of students within the school:
    - The pain point for this company was the excessive spending on paper, so I developed a solution and presented it to them.
    - The system included: Student registration, exam results, attendance, financial status, and enrollment,
        all carried out in one place, completely migrating from paper to digital.
    - Here, I went through the entire development cycle: Business rules, architecture, code design, development,
        testing, and deployment.
#### Benkyo Tech
    - Developed the API using Clean Architecture, isolating business rules, adhering to coding best practices such as Clean Code,
        using objective names and specific functions, and following the SOLID principles.
    - Used Java 17 as the language and Spring Framework, Spring JPA for database, Spring Security for JWT token
        and access levels, and Log4j for log monitoring.
    - Classes tested using JUnit and Mockito, maintaining a minimum code coverage standard of 80%.
    - PostgreSQL as the database.
    - Graphical interface built with Angular, TypeScript, HTML, and CSS.

### Bakery
#### Bakery HR
    - The second was a time tracking system developed for a market.
        The client's main problem was the time spent accounting for the hours registered on paper,
            and at the same time, the company wanted employee data on the system as well (documents, salaries, roles).

    - The system registers employees and their data, has access levels according to their role,
        calculates overtime, and informs whether the employee has extra hours or is in debt.

#### Bakery Tech
    - In this project, I used Kotlin on the backend along with Spring to create the API, using Clean Architecture and best practices.
    - Spring Security with JWT, resources restricted to specific roles.
    - PostgreSQL as the database, and unit tests using JUnit and Mock.

## Act
    - Worked in the loan sector.
    - Created microservices and improved existing APIs, always applying best programming practices
        such as Clean Code and the SOLID principles. Worked with Clean Architecture, Java, and Spring.
        Provided support for APIs and resolved production issues.
### Act Tech
    - Worked with microservices with Clean Architecture and Hexagonal Architecture, using Java 21 and 17 with Spring Framework.
    - Created jobs to automate tasks that did not require human actions.
    - Using Oracle and Redis databases (for caching).
    - Azure for pipeline and repository, and Sonar for test validation.
    - Kafka as the messaging system.

## Why Change?
    - I researched the company and believe it offers interesting opportunities for my career.
    - Working with another language is very interesting to me, and
        it is an experience that will help me grow professionally.

## Confrontation Situation
    - A feature was merged into production based on a branch with "dirty code."
    - Another colleague suggested that I, since I was without a task at the moment, use Git to find the "dirt" and clean it.
    - I opposed this, suggesting it would be more efficient to fetch the last version in production and redo the new feature.
    - We reached an impasse and brought the issue to the Tech Lead, who also agreed that redoing the task was more efficient and safe.
    - I completed it within a few hours. However, during this process, I had to engage in significant dialogue to convince them of my solutio
# **************************
# JAVA
## CORE
### Class and Objects
    - CLASS: Model to create objects, defines attributes and methods that objects will have
    - OBJECTS: Instance of a class, represents the concrete element of the attributes defined by the class
    - CONSTRUCTORS: Method called when the object is created, initializes object attributes
    
    - ACCESS MODIFIERS
        * public: Accessible from anywhere.
        * private: Accessible only within the class itself.
        * protected: Accessible within the same package and by subclasses.
        * default (no modifier): Accessible only within the same package.
### Interface and Abstract

#### INTERFACE:
    - Contract that defines methods that the class must implement
        * Interface methods are public and abstract (can also have default and static methods)
        * Contains no attributes, only constants (public static final)
        * A class can implement multiple interfaces

#### ABSTRACT CLASS:
    - Cannot be instantiated, can have abstract and concrete methods
        * Serves as a base for other classes
        * Can contain any access modifier

#### DIFFERENCES
        * Inheritance
            interface: Implemented by multiple classes
            abstract: Inherited by only one class
        
        * Methods
            interface: Only abstract until Java 8
            abstract: Abstract and concrete

        * Attributes
            interface: Only constants
            abstract: Normal and constants
        
        * Constructors
            interface: Does not have constructors
            abstract: Can have constructors
        
        * Main Use
            interface: Define contracts
            abstract: Create a base for code reuse
### OOP
#### Benefits
    - Reusability with inheritance and polymorphism
    - Maintainability with encapsulation

#### OOP Concepts
    * Encapsulation
        - Protects class data, avoids scope leakage
        - Exposes necessary data through public getter and setter methods

    * Inheritance
        - Allows a class to inherit attributes and methods from another class
    
    * Polymorphism
        - The ability of an object to take on different forms
        
        - Types:
            Overloading (Compile-time)
            - When the subclass redefines a method already declared in the parent class
            - Same signature (name, return type, and parameters) as the parent class

            Overriding (Runtime)
            - Several methods in the same class have the same name but different signatures
            - The goal is to have ways to execute the same method depending on the arguments passed

    *** this = reference to the current object
    *** super = reference to the parent class
__
## Collection
### List
    - Ordered list that can contain duplicate elements
        * ArrayList: fast access
        * LinkedList: linked list, efficient insertion and removal
### Set
    - Does not allow duplicate elements
        * HashSet: Unordered
        * LinkedHashSet: Maintains insertion order
        * TreeSet: Ordered naturally or by a comparator
### Map
    - Collection of Key-Value pairs
        * HashMap: Unordered, allows null values
        * LinkedHashMap: Maintains insertion order
        * TreeMap: Ordered by keys naturally or by a comparator
### When to Use
    - List: Order matters and duplicates are allowed
    - Set: No duplicates are desired
    - Map: Need to associate keys with values
__
## Stream API
    - Does not store data: Processes on demand
    - Immutable: operations do not change the original data source
### Operations
        - Intermediate: Transforms one Stream into another Stream, executed only when a terminal operation is performed
```text
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
List<Integer> evenNumbers = numbers.stream()
                                    .filter(n -> n % 2 == 0)
                                    .collect(Collectors.toList());
```
        - Terminal: Ends Stream processing and produces a result
```text
List<String> collected = Stream.of("a", "b", "c")
                               .collect(Collectors.toList());
```
### Exemplos
```text
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
List<Integer> evenNumbers = numbers.stream()
                                    .filter(n -> n % 2 == 0)
                                    .collect(Collectors.toList());
******************************************************************
List<Integer> sorted = numbers.stream()
                              .sorted()
                              .collect(Collectors.toList());
******************************************************************
```
__
## Lambdas
    - Used to manipulate collections
    - Shorter and more readable code
    - Integration with Stream API makes collection processing more functional
```javascript
                    (parametro1, parametro2) => { 
                        // corpo do método
                        return valor; 
                    }
```
## Java Memory Model
    - Defines how threads interact with shared memory
    - JMM establishes:
        * Visibility: Which changes made by one thread to a variable are visible to another thread
        * Synchronization: How memory operations can be reordered
        * Atomic access: Actions performed indivisibly, cannot be interrupted

    - Problems JMM solves:
        * Without JMM, changes made by one thread might not be visible to others,
          causing unpredictable behavior
## Garbage Collection
    - Frees memory occupied by objects that are no longer accessible
        * Ensures the application does not suffer memory leaks
        * Relieves the developer from manually managing allocation and deallocation
## Reflection API
    - Allows:
        * Inspecting and manipulating classes, methods, attributes, and constructors at runtime
        * Dynamically creating class instances
        * Invoking methods and accessing private or protected fields

    - Useful when the program's behavior needs to be dynamically altered

    - Frameworks and Libraries:
      * Hibernate: Uses Reflection to map Java objects to database tables
      * Spring: Uses Reflection for dependency injection and proxy creation
      * JUnit: Uses Reflection to automatically execute test methods
# **************************
# BEST PRACTICES
## Clean Code
    - Clear Naming: Names must be self-explanatory. Avoid abbreviations or generic names
    - Small Methods: Methods should perform specific tasks
    - Avoid Unnecessary Comments
    - Avoid Code Duplication: Promote method reuse
    - Avoid Methods with Many Parameters
## S.O.L.I.D
### Advantages
    - Modular Code: Facilitates adding new features
    - Easier Testing: Decoupled classes are easier to test
    - Simplified Maintenance: Reduces the impact of code changes
### Single Responsibility
    - A class should have only one reason to change
    - Objective: Keep classes focused on a single task
    - Advantage: Simplifies maintenance and understanding
### Open/Closed Principle
    - Classes should be open for extension but closed for modification
    - Objective: Add new features without modifying existing code, avoiding side effects
    - Advantage: Prevents unpredictable behavior in the code
### Liskov Substitution
    - Subclasses should be replaceable by their superclass without altering the behavior
    - Objective: Ensure the subclass maintains the expected behavior of the base class
### Interface Segregation
    - Classes should not be forced to implement methods they do not use
    - Objective: Divide large interfaces into smaller, more specific ones
### Dependency Inversion
    - Classes should depend on abstractions (interfaces) rather than concrete implementations
    - Objective: Decouple classes
## Design Patterns
### Advantages
    - Simplifies Software Design
        * Provides clear solutions to recurring problems
    - Decoupling
        * Improves modularity, facilitating future changes
### Creational
    - Focused on object creation
    * Singleton:
        - Ensures a single instance and provides a global access point
    * Factory:
        - Defines an interface for creating objects, allowing subclasses to decide which class to instantiate
### Structural
    - Deals with class and object composition and structuring
    * Adapter:
        - Enables two incompatible classes to work together by adapting one interface to another
### Behavioral
    - Focused on communication and interaction between objects
    * Strategy: Defines a family of algorithms, encapsulates each one, and
        - Makes them interchangeable at runtime, e.g., Observer, Command
## Architecture
### Concept
    - Aims to organize code so that business rules (domain) are isolated from implementation details
    - Changes in the database, UI technology, or external frameworks do not affect the application's core
    - Allows testing the domain simply without relying on infrastructure
    - Maintainable, Testable, and Flexible
### Dependency Rules
    - Inner layers should not import anything from outer layers
    - Dependencies should flow from outside to inside
### Differences Clean vs. Hexagonal
    - Hexagonal focuses more on the separation between cores and adapters
    - Clean Architecture includes more specific layers like application and entities
#### Clean Architecture
    * Uses the dependency inversion principle
        - Use case depends on an internally declared interface, not on a specific database repository
        - The concrete implementation of this repository (using a persistence framework) is in the external layer
        - This way, the UseCase does not know the framework; it only uses the interface

#### Layers
    - Represented by concentric circles (ring model)
    - Each outer circle can depend on the inner circle but never the reverse
    
    * Business Rules (Entities/Domain) -> Use Cases -> Interface Adapters -> Frameworks and Drivers
    
    * Business Rules (Entities/Domain): Central layer, does not know about DB, Web, or anything external
    
    * Use Cases: Orchestrate/Coordinate data flow between entities and the external layer, defining application rules
        But still independent of technical details, may depend on the Entity layer to manipulate domain objects
    
    * Interface Adapters: Translates data from the format used by USE CASE and ENTITY 
        to a format more appropriate for external tools 
        
        Here are concrete repositories, controllers, DTOs
        
        May contain frameworks like ORM to bridge between entities and the database

    * Frameworks and Drivers: Outer layer, infrastructure details like databases, libraries, frameworks, and drivers
### Hexagonal Architecture
#### Layers
    - CORE: Business rules and domain models
        * Domain: Entities, Value Objects
        * Application: Use cases that orchestrate the flow of business logic
    
    - PORTS: Interfaces that the core exposes for communication with the external world or expects to receive
        * Input Port: Receives commands from the external world (REST, CLI, events)
            - Represents how the core is triggered

        * Output Port: Sends data or commands to external components (DB, APIs)
            - Interface that the core uses to invoke external services

    - ADAPTERS: Concrete implementations of Ports
        * Input Adapters: REST Controller that translates HTTP requests to a Use Case
            - Implement input ports
        * Output Adapters: Repository that implements the interface to access DB, external services
            - Implement output ports
## TDD
    - Objective: Ensure that the written code is always testable and works as expected
    - Advantages:
        * More modular code, fewer potential bugs
        * Reliable Refactoring: Changes can be made confidently as tests verify expected behavior remains valid
### Cycles
    - Red (Write the Test): The test must fail because the functionality does not exist yet
    - Green (Implement Functionality): Write the simplest code for the test to pass
    - Refactor: Improve the code implementation without altering the tested behavior
    - Repeat the process by adding new tests and expanding functionality

### Possible Questions
#### Simple
    - TDD vs. Conventional Testing
        A: TDD writes the test first; in conventional testing, the test is done after implementing the functionality

    - Describe the Cycle
        A: RED: Write the failing test, GREEN: Write enough code for the test to pass, REFACTOR: Improve the code

    - Advantages:
        A: Improves quality, reduces bugs, facilitates safe refactoring

    - Example:
        A: Test that checks if a number is even (using assertTrue),
            followed by code returning a boolean that calculates if the parameter divided by two has a remainder of 0

    - TDD and Software Design
        A: TDD promotes modular and testable code, encouraging better separation of responsibilities

    - "Explain how to avoid external dependencies in unit tests."
        A: By using Mocks for dependencies and isolating the behavior of the tested code
## DDD
    - Approach focused on understanding and modeling business logic in a way that it aligns with the domain
#### Benefits
    - Helps manage complexity by focusing on the business domain
    - Improves communication between developers and domain experts
#### Concepts
    - Domain: Core business activity for which the software will be developed
    - Domain Model: Abstract representation of the domain, represents entities, behavior, and business rules
    - Ubiquitous Language: Common language used by domain experts and developers, avoiding misunderstandings
    - Bounded Context: Divides the domain into smaller, manageable subdomains with defined boundaries
    - Domain Event: Actions or changes in the domain state, used in asynchronous communication
#### Architectural Layers
    - Domain Layer: Business rules and main system logic
    - Application Layer: Does not contain business logic, coordinates tasks, and delegates work to lower layers
    - Infrastructure Layer: Technical aspects, data persistence, frameworks, external systems
#### DDD Elements
    - Entity: Objects with unique identity and lifecycle, e.g., Customer, Order
    - Value Objects: Immutable objects representing domain concepts without their own identity, e.g., Address
    - Aggregates: Group of objects treated as a unit, with a Root Entity controlling consistency
    - Services: Used for operations that do not fit into Entities or Value Objects but belong to the domain
# **************************
# DATABASES
## Relational
### Concept
    - Organized in a tabular structure (tables / relationships)
    - Tables related to each other through foreign and primary keys
    
    * Relational Integrity: Rules ensure data integrity
        - Primary key: Ensures each record is unique in the table
        - Foreign key: Relates tables and maintains referential consistency between them
### ACID
    - Atomicity: The transaction is fully completed or not performed at all
    - Consistency: The database remains in a valid state after a transaction
    - Isolation: Parallel transactions do not interfere with each other
    - Durability: Data persists even after a failure
### Joins
#### Summary
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
### Querys
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
## Não Relacional
    - Does not use tables, rows, and columns as its primary structure
      - Data is stored as documents, key-value pairs, graphs, or wide-columns
    
      * Characteristics of NoSQL
      - Flexibility: Can store structured, semi-structured, and unstructured data
      - Horizontal Scalability: Add more servers to handle increased data
      - High Performance: Optimized for fast read and write operations at scale

### Types of NoSQL
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

### Exemplos
```text -> APLICAÇÂO 
Banco               | Type           | Use Case
MongoDB             | Document       | Web applications, flexible data, logs
Redis               | Key-Value      | Caching, queues, sessions
Neo4j               | Graph          | Social networks, recommendation systems
Apache Cassandra    | Wide-Columns   | Data warehouses, IoT, large data volumes
DynamoDB            | Key-Value/Doc  | Highly scalable systems
HBase               | Wide-Columns   | Distributed large data volumes
```
### SQL vs NOSQL
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
# DOCKER
## Main Components
    - IMAGE: A read-only template defining everything needed to run a container
        * Includes the OS, libraries, dependencies, and the application itself
    - Container: A running instance of an image
    - Docker:
        * File: A script file to automate image creation
        * Compose: An orchestrator for multiple containers defined in a single file (docker-compose.yaml)
        * Registry: Repository to store and share Docker images
    - Volume: Persistent storage system for containers, retains data even if the container is recreated
## Advantages
    - Portability: Containers run consistently across environments (local, server, or cloud)
    - Lightweight: Containers share the OS kernel, consuming fewer resources than virtual machines
    - Scalability: Simplifies creating and managing applications with orchestrators like Kubernetes
    - Ensures identical environments for team collaboration
## Networking and Volumes
### Networking
    - `docker network`: Command to manage container networking
        - If not specified, the container is automatically assigned to the `bridge` network
### Volumes
    - Persistent storage that retains files across container restarts or recreations
## Example
    - Java image creation with Gradle
```dockerfile
# Use a base image with Java 21
FROM eclipse-temurin:21-jdk-alpine

# Set environment variables to avoid installation prompts
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=UTC

# Working directory inside the container
WORKDIR /app

# Copy the Gradle build to the container
COPY build/libs/kronos-time-tech-0.0.1-SNAPSHOT.jar app.jar

# Expose the port used by the application
EXPOSE 8080

# Command to run the application
ENTRYPOINT ["java", "-jar", "app.jar"]
````
# **************************
