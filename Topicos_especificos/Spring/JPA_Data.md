### JPA Teoria
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
                        List<Customer> findByLastName(@Param("lastName") String lastName); T
# Carregamento de entidades
## Qualquer Para Um: EAGER
            - A entidade associada à entidade buscada, vem junto na consulta
            - Vai ser um select na tabela e um Left join, Logo retorna as duas
            - Mesmo que a chamada nao envolva a outra tabela por baixo dos panos será feita a consulta
                com join
## Qualquer Para Muitos: LAZY
            - Se for  para muitos, entidade associada à entidade buscada, não vem junto na consulta
            - Lazy faz o JPA realizar novas consultas no banco confirme a necessidade da chamada
                -EX: produto de um setor. 
                        primeiro da um select no setor, de pois outra consulta na lista de produtos
## Alterando Comprotamento
### Join Fetch
    - Resolve o problema das N+1 Consultas
    - Não funciona para buscas paginada do Spring
    - @Query("SELECT apelido FROM NomeDaClasse) => Também busca no modo LAZY
    - @Query("SELECT apelido FROM NomeDaClasse apelido JOIN FETCH apelido.atributoOutraTabela)
            => Modo otimizado, evitando idas ao banco
#### N+1 consultas junto de paginação
    - Paginação do Spring pega o limit de linhas da tabela
    - Para paginação do spring, precisa de uma query personalizada
        para não ter n+1 consultas e paginação
    - No sql, 
        * teria de buscar todos os produtos da tabela produto
        * Fazer um inner join com categoria relacionando os ids
        * e uma clausula IN no product delimitando q quantidade de produtos retornados
```text JPQL
    @Query("SELECT apelido FROM NomeDaClasse 
        apelido JOIN FETCH apelido.categories WHERE apelido IN :produto)
        
        List<Produto> findProductsCategories(List<Product> product)
        Usa o recurso join fetch para evitar o problema N+1 consultas no BD
        e a clausula IN especificiando quem sera limitado pela paginação do spring 
```
### Consulta Customizadas
    - Query Method
        * consulta customizada pelo nome do metodo => public<Person> findByName(String name)

    - JPQL (Parecida com SQL)
        * @Query("SELECT apelido FROM NomeDaClasse apelido WHERE apelido.atributo) 
        * Vantagem
            - Consultas podem ser mais simples
            - Usufrui melhor do Spring Data JPA
            - Os objetos resultantes são entidades gerenciadas pela JPA
        * Desvantagem
            - Consultas complexas podem ser dificies de escrever e validar
            - Não tem união (JPA 2.x)
### CountQuery
    - Outra forma de usar paginação do spring
```text JPQL
    @Query("SELECT apelido FROM Produto 
        apelido JOIN FETCH apelido.categories WHERE apelido IN :produto
        countQuery = "SELECT COUNT(apelido)
         FROM Produto apelido JOIN apelido.catrgories 
        )
           
        List<Produto> findProductsCategories(List<Product> product)
        Usa o recurso join fetch  e countQuery para evitar o problema N+1 consultas no BD
         
```
    
### Transaction
    - spring.jpaopen-inview=false: Não permite operação de ORM no controlador
        * Faz com qu a sessão JPa seja encerrada antes de voltar para camada controller
    - Assegura resolução de transação com banco e de todas pendencias LAZY