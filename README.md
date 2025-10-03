# DSList API

## Visão Geral

O DSList é um projeto de API RESTful desenvolvido em Java com Spring Boot, projetado para organizar e gerenciar listas de jogos. Ele permite a criação, visualização e manipulação de listas de jogos, bem como a consulta detalhada de jogos individuais. Este projeto demonstra a aplicação de conceitos de desenvolvimento back-end, incluindo a construção de uma API, a modelagem de um banco de dados relacional e a implementação de uma arquitetura em camadas.

## Funcionalidades Principais

* **Listagem de Jogos:** Endpoint para consultar todos os jogos cadastrados no banco de dados.
* **Detalhes do Jogo:** Endpoint para buscar informações detalhadas de um jogo específico por seu ID.
* **Listas de Jogos:** Endpoint para consultar todas as listas de jogos disponíveis.
* **Jogos por Lista:** Endpoint para consultar todos os jogos que pertencem a uma lista específica.
* **Mover Jogos na Lista:** Endpoint que permite alterar a posição de um jogo dentro de uma lista, demonstrando a manipulação de dados e a lógica de negócios.

## Modelo de Domínio

O modelo de domínio do DSList é composto por duas entidades principais: `Game` e `GameList`. O relacionamento N-N entre elas é gerenciado pela entidade associativa `Belonging`, que também armazena a posição de cada jogo na lista.

![image](https://github.com/user-attachments/assets/728f0c07-5379-48f1-bbf6-60d0e60b824c)

## Arquitetura do Projeto

O projeto foi estruturado em camadas para garantir a separação de responsabilidades e a manutenibilidade do código:

* **Controllers:** Responsáveis por expor os endpoints da API e lidar com as requisições HTTP.
* **Services:** Contêm a lógica de negócios da aplicação.
* **DTOs (Data Transfer Objects):** Utilizados para transferir dados entre as camadas, evitando a exposição das entidades do banco de dados.
* **Repositories:** Camada de acesso a dados, utilizando o Spring Data JPA para interagir com o banco de dados.
* **Entities:** Classes que mapeiam as tabelas do banco de dados.

## Tecnologias Utilizadas

* **Java 21**
* **Spring Boot 3.4.1**
* **Spring Data JPA:** Para persistência de dados.
* **Maven:** Para gerenciamento de dependências.
* **H2 Database:** Banco de dados em memória para testes e ambiente de desenvolvimento.
* **PostgreSQL:** Banco de dados utilizado em produção.
* **SQL:** Scripts de inserção de dados iniciais.

## Como Executar o Projeto

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/igorpintos/dslist.git](https://github.com/igorpintos/dslist.git)
    ```
2.  **Acesse o diretório do projeto:**
    ```bash
    cd dslist
    ```
3.  **Execute o projeto com o Maven:**
    ```bash
    ./mvnw spring-boot:run
    ```
4.  A aplicação estará disponível em `http://localhost:8080`.

## Endpoints da API

* `GET /games`: Retorna a lista de todos os jogos.
* `GET /games/{id}`: Retorna os detalhes de um jogo específico.
* `GET /lists`: Retorna todas as listas de jogos.
* `GET /lists/{listId}/games`: Retorna os jogos de uma lista específica.
* `POST /lists/{listId}/games`: Move um jogo de uma posição para outra dentro de uma lista.
  
