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
### Simple
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
# HIBERNATE
    - Object-Relational Mapping (ORM) framework that abstracts persistence operations
        by converting classes and relationships into tables and columns and vice versa

    - JPA is a specification that defines how ORM should work
        Hibernate is an implementation of this specification, providing the engine for persistence
# **************************
# RELATIONAL
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
# **************************
# RESTFUL WEB
## REST
    - An architectural style that defines a set of constraints for web services
    Principles:
        - Client-Server: The client makes requests, and the server processes and responds
        - Stateless: The server does not store the client state between requests
        - Uniform Interface: REST uses standard HTTP methods to interact with resources
## REST-Full
    - Implements REST principles, based on HTTP, and uses HTTP methods (GET, POST, DELETE, PUT)
    - Supports JSON or XML formats
    
    * Advantages
        - Simplicity: Easy to understand and implement, as it uses familiar HTTP conventions.
        - Interoperability: Can be used by any client that supports HTTP, such as browsers, mobile apps, etc.
        - Independence: Client and server can evolve independently.
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