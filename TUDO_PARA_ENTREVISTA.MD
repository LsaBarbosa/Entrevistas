# RH
## Experiencias
### Itau
#### Itau RH
    - Iniciei minha carreira trabalhando no Itaú, minha primeira experiencia no setor financeiro.
        Lá, desnvolvi e sustentei serviços com Clean Architecture e pude colocar nesses serviços
            boas práticas programação, como Clean Code e os princípios SOLID.

    - Além disso, monitorei, mantive e melhorei APIs utilizando Java, Spring Framework
    - Tembém desevolvimento de testes usando mockito e Junit, garatindo cobertura de no min 80%
    - Forneci sustentação as Apis, tendo apoio dos frameworks Splunk e grafana, para logs e saude das apis 
        bem como ferramentas de teste como JUnit e Mockito.
#### Itaú Tech
    - Realizei implementaçõs de features em APIs utilizando Java e Spring, observando as melhores práticas de programação
        * Como: Nomes significativos, funções curtas e com objetivos específicos
    
    - Além observar as regras de uso do clean arch, separando as regras de negócio do restante da aplicação
        * Usando interfaces e separação por modulos
    
    - Fiz sustentação nas aplicações além de monitorar o ambiente de produção
        * usando Splunk para verificar logs, grafana e kubbernets para verificar o estado da aplicação
    
    - Criei e atualizei documentações no Confluence, além de mapear algumas apis no openAPI
    - Banco de dados Postgres, SQLServer e Redis para cache
### B2B
    - Após essa experiência, trabalhei com contratos no modelo B2B.
    - Desenvolvi algumas páginas comerciais, para empresas locais utilizando Angular, React e TypeScript.
        com isso desenvolvi muito minhas habilidades de comunicação e gestão de tempo, e solução de problemas
        mas dois projetos foram mais relevantes para mim.
#### Benkyo
##### Benkyo RH
    - O primeiro foi um sistema escolar que gerencia toda a vida dos estudantes dentro da escola:
    - A dor dessa empresa era que havia muito gasto com papel, então desenvolvi uma solução e apresentei a empresa.
    - O sistema continha: Cadastro de alunos, resultados de provas, presença, situação financeira, matrícula
        tudo realizado em um único lugar migrando completamente do papel para o digital.
    - Essa experiencia me fez crescr como desenvolvedor pois passei por todo ciclo de desenvolvimento:
        - Regras de negócio, escolha de solução, arquitetura, design de código, desenvolvimento, Teste e deploy.
        - Além de fortalecer mais ainda minhs capacidades de comunicação, resolução de problemas, gestão de tempo
        -> Java 17, Spring Data, Security, Boot, Postgres(SQL), Clean Arch, testes unitários e boas práticas 
##### Benkyo Tech
    - Desenvolvi a Api usando Clean Arch, isolando as regras de negócios, observando as boas práticas de código como clean code
        usando nomes objetivos e funções específicas. além de observar o princípio do SOLID
    - Usei Java 17 como linguagem e Spring Framework, Spring jpa para banco de dados, spring security para uso de token JWT 
        e níveis de acesso, além do uso do Log4j para monitoração dos logs
    - Classes testadas usando Junit, Mockito mantendo um padrão mínimo de 80% de cobertura de código
    - Postgrees como banco de dados
    - Interface gráfica construída com Angular, typeScript e html e Css
#### Padaria
##### Padaria RH
    - O segundo foi um sistema de controle de registro de horas desenvolvido para um mercado. 
        O principal problema do cliente era o tempo gasto contabilzando as horas de forma manual, além disso 
        a empresa queria os dados dos colaboradores no sistema tbm (documentos, salário, cargos, faltas)

    - O sistema registra funcionários e seus dados pessoais, possui níveis de acesso de a cordo com o cargo, 
        calcula horas extras e informa se o funcionário tem horas a mais ou em débito, registra faltas.
##### Padaria Tech
    - Nesse projeto utlizei o kotlin no back-end junto do Spring para ciração da Api, usando Clean Arch e boas práticas
    - Spring security com jwt, recursos permitidos para ROLEs específicas
    - Banco de dados Postgres, alem de testes unitários usando Junit e mock
### Act
    - Estava alocado no Banco Pan no setor de empréstimos.
    - Desenvolvi nova features no modelo arquitetural de microsserviços e fiz sustentação de APIs existentes,
        como sempre aplicando boas práticas de programação. atuei com Clean Architecture, Java e Spring.
        Dei suporte ao Tech Lead no Desenvolvimento de bugs fix para problmas em produção
#### Act Tech
    - Atuei com microserviços com arquiteturas Clean arch e hexagonal, usando java 21 e 17, com Spring Framework
    - Criei jobs para automatizar algumas tarefas que não exigiam ações humanas.
    - Usando Banco de dados Oracle e Redis (para chache)
    - Azure para pipeline e para repositorio, uso do sonar para validação de testes
    - Uso do Kafka como sistema de mensageria
### Por que mudar
    - Pesquisei sobre a empresa e acredito que ela oferece oportunidades interessantes para minha carreira.
    - Trabalhar com outra linguagem é algo muito interessante para mim e 
        é uma experiência que me fará crescer como profissional.
### Situação de confrotno
    - Foi mergeado uma feature em produçao baseado numa banch com uma sujeira.
    - Foi sugerido por um outro colega que eu, por estar sem task no momento, buscasse usando Git qual era a sujeira e limpasse
    - Eu me opus dizendo que seria mais eficiente, buscar a ultima versão em produção e refazer a nova feature
    - Ficamos nesse impasse e levamos ao Tech Lead, que também achou mais eficiente e seguro, refazer a tarefa.
    - Em algumas horas eu fiz. Mas durante esse processo tive de dialogar bastante para convencer da minha solução
# ==================
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
#### Clean Arch
    * Uso do princípio da inversão de dependencia
        - Use case depende de uma interface declarada internamente e não de um repositorio específico de banco
        - Implementaçao concreta desse repositorio (usando framework de persistencia) fica na camada externa
        - Desse modo UseCase nao conhece o framework ele apenas usa a interface

#### Camadas
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
### DDD
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
``
                @Query(
                    value = "SELECT * FROM customers WHERE age > :minAge",
                    nativeQuery = true
                )
                List<Customer> findAllOlderThanNative(@Param("minAge") int minAge);

        - Named Query: Consultas pre-definidas(JPQL ou nativo) que recebem um nomee ficam associadas à entidade
``
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
    - 
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
# BANCO DE DADOS
## Relacional
### Conceito
    - Organizado em estrutura tabular (tabelas / relacionamento)
    - Tabelas relacionadas entre si por meio de chaves estrangeiras e primárias
    
    * Integridade Relacional: Regras garantem a integridade dos dados
        - Chave primaria: garante que cada registro seja único na tabela
        - Chave estrangeira: Relaiona tabelas e mantém a consistencia referencial entre elas
### ACID
    - Atomicidade: A transação é completada totalmente ou não é feita
    - Consistencia: O Banco permanece num estado válido após uma transação
    - Isolamento: Transações paralelas nao interferem entre si
    - Durabilidade: Dados perssitem mesmo após falha
### Joins
#### Resumo
    JOIN	Comportamento
    INNER	Apenas registros correspondentes entre as tabelas.
    LEFT	Todos os registros da tabela esquerda, com NULL para não correspondentes.
    RIGHT	Todos os registros da tabela direita, com NULL para não correspondentes.
    FULL	Todos os registros de ambas as tabelas, preenchendo com NULL onde necessário.
    CROSS	Produto cartesiano de ambas as tabelas.
    SELF	Join entre uma tabela e ela mesma.

#### Exemplos
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
### Querys
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
## Não Relacional
### Conceito
    - Não usa Tabelas, linhas, colunas como estrutura principal
    - Dados em formas de documentos, pares chave-valor, grafos, ou colunas amplas
    
    * Caracteristica NoSQL
    - Flexibilidade: Pode armazenar dados estruturados, semi-estruturados, e nao estruturados
    - Escalabilidade Horizontal: Adiciona mais servidores para lidar com mais dados
    - Performance alta escala: Otimizado para leitura e escrita rápida, mesmo com grande volume de dados
### Tipos De NoSql
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
### Exemplos
```text -> APLICAÇÂO 
Banco	|       Tipo	    |   Caso de Uso Principal
MongoDB	|       Documento	|   Aplicações web, dados flexíveis, logs
Redis	|       Chave-Valor	|   Cache, filas, sessões
Neo4j	|       Grafo	    |   Redes sociais, sistemas de recomendação
Apache  |       Cassandra	|   Colunas Amplas	Data warehouses, IoT, grandes volumes de dados
DynamoDB|	Chave-Valor/Doc |	Sistemas altamente escaláveis e servidores
HBase	|   Colunas Amplas	|   Grandes volumes de dados distribuídos
```
### SQL vs NOSQL
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
# DOCKER
## Componentes Principis
    - IMAGEM: modelo somente leitura, define todo o necessário para executar um container
        * inclui Sistema operacional, libs, dependencia e o propio aplicativo
    - Container: Instancia em execuçã de uma imagem
    - Docker 
        * File: arquivo de script que automatiza a criação de imagem
        * Compose: Orquestrador de multiplos containers definidos em um único arquivo (Docker-compose.yaml)
        * Registry: Repositorio para armazenar e compartilhar iamgens Docker
    - Volume sistema de armazenamento persistente para container, mantem os dados mesmo recriando o container
## Vantagens
    - Portabilidade: aplicações empacotadas em container funcionam em qualquer ambiente(local, serviodr ou nuvem)
    - Leveza: Container compartilham o mesmo Kernel do SO, consumindo menos recursos que maquina virtual
    - Escalabilidade: facilita a ciração e gestão de aplicações por meio de orquestradores como kubernets
    - Permite que equipes trabalhem em ambientes identicos
## Redes e Volumes
### Rede
    - docker network: comando para rede que envolve o container
        - não especificando a rede, automaticamente atribuirá à bridge
### Volumes
    - Arquivos: docker exec para mostrar os arquivos 
    - 
## EXEMPLO
    - Criação de uma imagem em java com Gradle
```dockerfile
# Use uma imagem base com Java 21
FROM eclipse-temurin:21-jdk-alpine

# Configuração de variáveis de ambiente para evitar prompts de instalação
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=UTC

# Diretório de trabalho dentro do container
WORKDIR /app

# Copiar o build do Gradle para o container
COPY build/libs/kronos-time-tech-0.0.1-SNAPSHOT.jar app.jar

# Expor a porta que a aplicação usa
EXPOSE 8080

# Comando para rodar a aplicação
ENTRYPOINT ["java", "-jar", "app.jar"]
```
# ==================

# ////////////// ////////////  ENGLISH ///////////// ///////////////////// ///////////////////// ////////////// //////
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
# *************************
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