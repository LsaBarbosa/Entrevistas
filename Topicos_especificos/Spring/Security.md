# Teoria
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
# OAUTH2
    - Permite que usuário se autentiquem em apps usando serviços como google, gith, Face
    - Protocolo de autorização, que permite que apps tenham acesso limitado a recursos de usuario
        * Sem expor suas credenciais 
## Funcionamento
    - Resource Owner: Usuario concede permissão para acesso aos seus recursos protegidos
    - Cliente: O App que solicita acesso aos recursos protegido em nome do usuário
    - Authorization Server: Responsável por autenticar o User e fornecer token de acesso ao client
    - Resource Server: Servidor que hospeda os recursos protegidos e valida os tokens recebidos
## Vantagem
    - Xp do user simplificada: Login unico SSO usando contas existentes
    - Controle Granular de acesso: Permite definir escopos que cada app pode acessar
    - Compatibilidade em diferente dispositivos: APIs, Mobile, Web
# BCypt
    - Algoritmo de Hash para armazenar e proteger senhas
## Caracteristicas
    - Hashing com SAL embutido
        * SAL valor aleatorio adicionado a senha ants dela ser processada
        * Evitando ataques dicionárioe tabela arco-íris

    - Proteção contra força bruta: BCrypt é computacionalmente caro, torna ataques lento e inviáveis
    - Formato de Saída padrão: $2a$<CUSTO>$<SALT><HASH>
## Funcionamento
    - O usuário insere uma senha.
    - O sistema gera um sal aleatório.
    - A senha combinada com o sal é processada pelo algoritmo BCrypt.
    - O hash resultante é armazenado no banco de dados.
    - Para verificar uma senha, o sistema compara a senha inserida com o hash armazenado usando o mesmo algoritmo.