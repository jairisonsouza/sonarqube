# SonarQube Docker Setup

Este repositório contém a configuração para rodar o SonarQube e o PostgreSQL utilizando Docker Compose. O SonarQube é uma ferramenta popular para análise de código e qualidade de software.

## Introdução

O **SonarQube** é uma plataforma de código aberto que permite realizar inspeção contínua da qualidade do código. Ele analisa a base de código para detectar bugs, vulnerabilidades e "code smells". Ele também fornece métricas e relatórios detalhados que ajudam na manutenção da qualidade do código ao longo do tempo.

A configuração deste repositório usa o **Docker** para executar o SonarQube e o **PostgreSQL** como banco de dados para armazenar os dados do SonarQube.

## Tecnologias

- **SonarQube**: Plataforma de análise de código.
- **PostgreSQL**: Banco de dados relacional utilizado pelo SonarQube.
- **Docker Compose**: Ferramenta para definir e rodar aplicativos Docker com múltiplos containers.

## Pré-requisitos

Para utilizar este projeto, você precisará ter os seguintes itens instalados em sua máquina:

- **Docker**: [Instalar Docker](https://docs.docker.com/get-docker/)
- **Docker Compose**: [Instalar Docker Compose](https://docs.docker.com/compose/install/)

## Instalação

1. Clone este repositório:

    ```bash
    git clone https://github.com/jairisonsouza/sonarqube.git
    cd nome-do-repositorio
    ```

2. Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis de ambiente:

    ```env
    POSTGRES_USER=sonar
    POSTGRES_PASSWORD=sonarpassword
    POSTGRES_DB=sonar
    ```

3. Suba os containers utilizando o Docker Compose:

    ```bash
    docker-compose up -d
    ```

    O Docker Compose irá baixar as imagens necessárias e iniciar os containers do **SonarQube** e **PostgreSQL**.

4. Acesse o SonarQube pela URL:

    ```
    http://localhost:9000
    ```

    O login padrão é:
    - **Usuário**: admin
    - **Senha**: admin

    Você será solicitado a trocar a senha na primeira vez que acessar.

## Utilização

Após a inicialização dos containers, o SonarQube estará disponível para análise de projetos de código. Para utilizar o SonarQube, você pode configurar projetos dentro da interface web e usar o **SonarScanner** para realizar a análise do código. 

### Para adicionar um novo projeto:

1. Acesse o painel do SonarQube em `http://localhost:9000`.
2. Crie um novo projeto e siga as instruções para configurar o SonarScanner em seu projeto de código.

## Parar e Remover os Containers

Para parar os containers e remover os volumes associados, execute:

```bash
docker-compose down -v
```
