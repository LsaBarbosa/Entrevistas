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

# ENGLISH 

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