# JAVA
## CORE
### Class and Objects
    - CLASSE: Modelo para criar objetos, define atributos e métodos que os objetos terão
    - OBJETOS: É a instancia de uma classe, representa o elemento concreto dos atributos definidos pela classe
    - CONSTRUTORES: Método chamado quando o Objeto é criado, incializa atributos de um objeto
    - MODIFICADORES DE ACESSO
        * public: Acessível de qualquer lugar.
        * private: Acessível apenas dentro da própria classe.
        * protected: Acessível dentro do mesmo pacote e por subclasses.
        * default (sem modificador): Acessível apenas dentro do mesmo pacote.
### Interface and Abstract
#### INTERFACE:
    - Contrato que define metodos que a classe deve implementar
        * métodos da interface são publicos e abstratos ( pode default e estatico tbm)
        * Não contém atributo, apenas constantes ( public static final )
        * Uma classe pode implementar várias interfaces
#### CLASSE ABSTRATA:
    - Não pode ser instanciada, pode metodos abstratos e concretos
        * Serve com base para outras classes
        * Pode conter qualqer modificador de acesso
#### DIFERENÇAS
        * Herança
            interface: Implementada por varias classes
            abstrata:  Herdada por apenas uma classe
        
        * Metodos
            interface: Somente abstratos até o java 8
            abstrata:  Abstratos e concretos

        * Atributos
            interface: Apenas constantes
            abstrata:  Normais e constantes
        
        * Cosntrutores
            interface: Não possui
            abstrata:  Pode possuir
        
        * Uso Principal
            interface: Definir contratos
            abstrata:  Cria uma base para reutilização de código
### POO
#### Benefícios
    - Reutilização com Herança e polimorfismo
    - Manutenabilidade com encapsulamento
#### Conceitos POO
    * Encapsulamento
        - Protege daods de uma classe, Evita o vazamento de escopo
        - expondo o necessário por meio de metodos públicos get e setter

    * Herança
        - Permite que uma classe herde atributos e metodos de outra classe
    
    * Polimorfismo
        - Capacidade do objeto assumir formas diferentes
        
        - Tipos:
            Sobrecarga (Overload) (tempo compilação)
            - Quando a subclasse redefine um metodo ja declarado na classe pai
            - Mesma assinatura (nome, tipo de retorno e parsametro) da classe pai

            Sobrescrita (Override) (tempo execução)
            - Varios metodos na mesma classe tem mesmo nome mas assinaturas diferentes
            - Objetivo é ter formas de executar o mesmo metodo dependendo dos args passados

    *** This = referencia ao objeto atual
    *** super = referencia a classe pai
## Collection
### List
    - Lista Ordenada podendo conter elementos duplicados
        * ArrayList: acesso rápido
        * LinkedList: lista encadeada, inserção e remoção eficientes
### Set
    - Não permite elementos duplicados
        * HasSet: Não ordenado
        * LinkedHasSet: Mantem a ordem de inserção
        * TreeSet: Ordenado de forma natural ou por um comparador
### Map
    - Coleção de pares Chave-Valor
        * HashMap: Não ordenado, permite valor null
        * LinkedHashMap: MAntem ordem de inserção
        * TreeMap: Ordenado pelas chaves de forma natural ou por um comparador
### Quando Usar
    - List: Ordem importa e pode elementos duplicados
    - Set: Nao deseja elementos duplicados
    - Map: Precisa associar chaves a valores
## Stream API
    - Não armazena dados: Processa sob demanda
    - Imutável: as operações não alteram a fonte original dos dados
### OPERAÇÕES
        - Intermediaria: Transforma uma Stream em outra Stream, executada apenas quando uma operação terminal é executada
```text
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
List<Integer> evenNumbers = numbers.stream()
                                    .filter(n -> n % 2 == 0)
                                    .collect(Collectors.toList());
```
        - Terminais: Finalizam o processamento da Stream e prosuzem resultado
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
## Lambdas
    - Usadas para manipular coleções 
    - Código mais curto e legível
    - Integração com Stream Api, torna processamento de coleções mais funcional
```javascript
                    (parametro1, parametro2) => { 
                        // corpo do método
                        return valor; 
                    }
```
## Java Memory Model
    - Define como as threads interagem com a memoria compartilhada 
    - JMM estabelece
        * Visibilidade: quais mudanças feitas por uma thread em uma variável é visível para outra thread
        * Sincronização: Como as operações em memoria podem ser reordenadas
        * Acesso atômicos: Ações realizadas de forma indivisível, não podem ser interrompidas

    -Problemas que JMM resolve
        * Sem o JMM mudanças feitos por uma thread poderiam não ser visívies para outras thread,
            causando comportamentos imprevisíveis
## Garbage Collection
    - Libera memória ocupada por objetos que não são mais acessíveis
        * garante que a aplicação não sofra vazamento de memoria
        * Garante que o dev não precise gerenciar alocação e desalocação manualmente
## Reflection API
    - Permite
        * inspecionar e manipular classes, métodos, atributos e construtores em tempo de execução
        * Criar instancias de classe dinamicamente
        * Chamar metodos e acessar campos privados ou protegidos
    
    - Útil quando o comportamento do programa precisa ser alterado dinamicamente

    - FrameWorks e Libs
        * Hibernate: usa Reflection para mapear objetos Java em tabelas do BD
        * Spring: usa Reflection para injeção de dependencias e criação de proxies
        * Junit: usa Reflection para executar metodos de teste automaticamente
# ==================
# BOAS PRATICAS
## CleanCode
    - Nomenclatura Clara: Nomes devem ser autoeplicativos. Sem abreviação ou nomes genéricos
    - Pequenos Métodos: O Método deve realizar a tarefa específica
    - Evitar Comentários desnecessários
    - Evitar duplicação do código: Explore a reutilização de métodos
    - Evitar funções com muitos parametros
## S.O.L.I.D
### Vantagens
    - Codigo Modular: Facilita adição de novas funcionalidades
    - Facilidade de teste: Classes desaclopadas são amis faceis de testar
    - Manutenção simplificada: Reduz impacto de alterações no código
### Single Resposibility
    - Classe deve ter apenas um único motivo para mudar
    - Objetivo: manter as classes focadas em apenas uma tarefa
    - Vantagem: Facilita manutenção e entendimento
### Open Close
    - Classes abertas par extensão e fechadas para modificação
    - Objetivo: Adicionar novas features sem alterar o cod existente, evitando efeitos colateral
    - Vantagem: Evita impresivibilidades no código
### Liskov Substitution
    - Subclass devem ser substituivel por sua Superclasse sem alterar o comportamento
    - Objetivo: Garantir que a sublcass mantenha o comportamento esperado da class base
### Interface Segregation
    - Classe nao deve ser forçada a implementar metodos que não utiliza
    - Objetivo: dividir interfaces grandes em interfaces menores e específicas
### Dependency inversion
    - Classes devem depender de abstrações(interfaces) e nao implementaçoes concretas
    - Objetivo: Desacoplamento entre classes
## Pattern Project
### Vantagens
    - Facilita o design de Software
        * Prove soluções claras para problemas recorrentes
    - Desacoplamento
        * Melhora a modularidade, facilitando alteração no futuro
### Criacionais
    - Focados na criação de objetos
    * Singleton: 
        - Garante que tenha uma instancia e fornece um ponto global de acesso
    * Factory:
        - Define uma interface criar objetos, pertime que subclases decidam qual class instanciar
### Estruturais
    - Tratam da composição e estrutação de Classes e objetos
    * Adapter:
        - Permite que duas classes incompatíveis trabalhem juntas adaptandouma interface para outra
### Comportamentais
    - Focados na comunicação e interação entre objetos
    * Strategy : Define uma familia de algoritimo, encapsule cada um e 
        - torne-os intercambiáveis em tempo de excução, Observer, Command
## Arquitetura
### Conceito
    - Visa organizar o código para que regas de negócio (domínio) fiquem isolada do detalhe da implementação
    - Mudança em BD, na tenologia de UI, ou frameworks externos nao afetam o núcleo da aplicação
    - Testar o dominio de forma simples sem depender de infraestrutura
    - Manutenível, Testável e flexível
### Regras de dependencia
    - Camadas internas não podem importar nada das camadas externas 
    - Dependencias devem ir de fora para dentro
### Diferenças Clean X Hexa
    - Hexagonal foca mais na separação entre núcleos e adaptadores
    - Clean Arch inclui camadas mais específicas como aplication e entities
### Clean Arch
    * Uso do princípio da inversão de dependencia
        - Use case depende de uma interface declarada internamente e não de um repositorio específico de banco
        - Implementaçao concreta desse repositorio (usando framework de persistencia) fica na camada externa
        - Desse modo UseCase nao conhece o framework ele apenas usa a interface
##### Camadas
    - Representado por circulos concentricos(modelo de aneis)
    - Cada circulo externo pode depender do circulo interno, mas nunca o contrário
    
    * Regras de negócio (Entidades/Dominio) -> Use cases -> Interface Adapters -> Frameworks e Drivers
    
    * Regras de negócio (Entidades/Dominio): Camada mais central, não conhece BD, nem Web, nada externo
    
    * Use cases: Orquestram/Coordenam fluxo de dados entre entidades e a camada externa, define-se regras da aplicação
        mas ainda independente de detalhes técnicos, podem depender de camada Entidade, para manipular objetos de domínio
    
    * Interface Adapters: Traduz dados do formato usado pelos USE CASE e ENTIDADE 
        para um formto mais apropriado para ferramentas externa 

        Aqui vão repositórios concretos, controladores, DTOs
        
        Pode Conter frameworks como ORM para servir de ponte entre as entidades e o BD

    * Frameworks e Drivers: Camada mais externa, detalhes de infra estrutura como BD, Libs, Frameworks e drivers
### Hexagonal Arch
#### Camadas
    - CORE OU NÚCLEO: Regras de negócio e modelos de dominio
    - coração do sistema composto por:
        * Dominio: Entidades, Objeto de valor
        * Aplicação Casos de uso, que orquestram o fluxo da lógica de negócio
    
    - PORTS OU PORTA: Interfaces que o núcleo expoem para comunicação com mundo externo ou espera receber
        * Porta de entrada: Recebe comandos do mundo externo (Rest,CLi, eventos)
            - Representa como o núcleo é acionado

        * Porta de saída: Pra enviar dados ou comando para componentes externos (BD, APIs)
            - Interface que o núcleo utiliza para invocar serviços externos

    - ADAPTERS OU ADPTADORES: Implementações concreta das Portas
        * Adaptadores de entrada: Controlador Rest que traduz a requisição HTTP para um Use CASE
            - Implementam as portas de entrada
        * Adaptadores de saída: Repositorio que implementa interface para acessar BD, serviços externos
            - Implementam as portas de saída[
## TDD
    - Objetivo fazer com que o código escrito sempre seja testável e que funcione como esperado
    - Vantagens: 
        * Código mais modular, menos possíveis bugs
        * Refatoração confiável: a mudança pode ser feita com confiança, pois os testes verificam se o compotamento esperado continua válido
### Ciclos
    - Red (Escreva o Teste): o teste deve falhar, pois a funionalidade testada não existe
    - Green (implemente funcionalidade): Escreva o codigo mais simples para o teste passar
    - Refector: melhore a implementação do codigo, sem alterar o comportamento testado
    - Repita o processo adicionando novos testes e expandindo funconalidades

### Perguntas possíveis
#### Simples
    - TDD x Teste convencional
        R: TDD o teste é escrito antes, no teste comum é feito após a implementação da funcionalidade

    - Ciclo descreva
        R: RED: escreva o teste que falha, GREEN: escreva código suficiente para passar no teste, Refactor melhore o código

    - Vantagens: 
        R: Aumenta qualidade , reduz bugs, facilita refatorações seguras

    - Exemplo:
        R: teste que verifica se os numeros são par (usando um assertTrue), 
            depois um codigo,com retorno boolean que calcula a variavel vinda no parametro divida por dois tem resto 0

    - TDD e Desing de Software
    R: TDD incentiva código modular e testavel, gerando melhor separação de responsabilidades

    - "Explique como evitar dependências externas em testes unitários."
    R: usando Mocks para as dependencias e isolar o comportamento do codigo testado
## DDD
    - Abordagem que foca em compreender e modelar a logica de negocio de maneira que ela esteja conectada ao dominio
#### Benefícios
    - Ajuda a lidar com a complexidade ao focar no domino do negócio
    - Melhora a comunicação entre dev e especialista de dominio
#### Conceito
    - Domínio: Atividade principal do negócio para qual o software será desenvolvido
    - Modelo de Domínio: Representação abstrata do dominio, representa entidade, comportamento e regras de negocio
    - Linguagem Ubiqua:Linguagem comum usada por especialistas do dominio e devs, evita mal entendido
    - Bounded Context: Divide o dominio em subdomnios menores e gerenciaveis com limites definidos
    - Evento de dominio: Ações ou mudanças no estado do dominio, usados em comunicação assincrona
#### Camada Arquitetural
    - Camada Domínio: Regra de negócio e lógica principal do sistema
    - Camada Aplicação: Mão contem lógica de negócio, coordena tarefas e delega trabalho às camadas abaixo
    - Camada Infra: Aspectos técnicos, persistencia de dados, framework, sistemas externos
#### Elementos do DDD
    - Entidade: Objetos com identidade única e ciclo de vida, exemplo Cliente, Pedido
    - Objetos de Valor: Objetos imutáveis, representam conceitos do dominio, sem identidade propia, ENDEREÇO
    - Agregados: Conjunto de objetos que são tratados como uma unidade, com uma entidade Raiz controlando a consistencia
    - Services: Usado para operações que nao se encaixam em Entidades ou objetos de valor, mas pertencem ao dominio
# ==================

# ENGLISH
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

##### Layers
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
# *************************