# Projeto de Login e Registro com Spring Boot

Este é um projeto simples de API REST para registro e login de usuários, construído com Spring Boot. Utiliza Spring Security para a criptografia de senhas e um banco de dados em memória (H2) para facilitar a execução e os testes sem a necessidade de configuração externa.

## Tecnologias Utilizadas

-   **Java 17**
-   **Spring Boot**
-   **Spring Web:** Para criar os endpoints REST.
-   **Spring Security:** Para segurança e criptografia de senhas (BCrypt).
-   **Spring Data JPA:** Para persistência de dados.
-   **H2 Database:** Banco de dados em memória para ambiente de desenvolvimento.
-   **Lombok:** Para reduzir código boilerplate (getters, setters, etc.).
-   **Maven:** Para gerenciamento de dependências.

## Como Baixar e Executar o Projeto

Siga os passos abaixo para baixar o código do GitHub e rodar a aplicação localmente.

### Pré-requisitos

-   Git instalado.
-   JDK 17 ou superior instalado.
-   Maven instalado.

### Passos

1.  **Clone o repositório** para a sua máquina local usando o seguinte comando no terminal:
    ```bash
    git clone [https://github.com/davitonn2/spring-boot-auth-api.git](https://github.com/davitonn2/spring-boot-auth-api.git)
    ```

2.  **Navegue até a pasta do projeto** que foi criada:
    ```bash
    cd spring-boot-auth-api
    ```

3.  **Execute o projeto** com o Maven:
    ```bash
    mvn spring-boot:run
    ```

4.  Pronto! A API estará rodando em `http://localhost:8080`.

## Endpoints da API

Use ferramentas como Postman, Insomnia ou `curl` para testar os endpoints.

### 1. Registrar Novo Usuário

Cria um novo usuário no sistema.

-   **URL:** `/api/auth/register`
-   **Método:** `POST`
-   **Body (JSON):**
    ```json
    {
        "name": "Nome do Usuário",
        "email": "usuario@exemplo.com",
        "password": "senhaforte123"
    }
    ```
-   **Resposta de Sucesso (200 OK):** `"Usuário registrado com sucesso!"`
-   **Resposta de Erro (400 Bad Request):** `"Erro: Email já está em uso!"`

---

### 2. Autenticar Usuário

Autentica um usuário existente e retorna uma mensagem de sucesso.

-   **URL:** `/api/auth/login`
-   **Método:** `POST`
-   **Body (JSON):**
    ```json
    {
        "email": "usuario@exemplo.com",
        "password": "senhaforte123"
    }
    ```
-   **Resposta de Sucesso (200 OK):** `"Login bem-sucedido!"`
-   **Resposta de Erro (400 Bad Request):** `"Erro: Usuário não encontrado!"` ou `"Erro: Senha inválida!"`

## Acessando o Banco de Dados (H2 Console)

Como o projeto usa um banco de dados em memória, você pode visualizá-lo diretamente pelo navegador enquanto a aplicação está rodando.

1.  Acesse a URL: [http://localhost:8080/h2-console](http://localhost:8080/h2-console)

2.  Na tela de login, use as seguintes informações:
    -   **Driver Class:** `org.h2.Driver`
    -   **JDBC URL:** `jdbc:h2:mem:testdb`
    -   **User Name:** `sa`
    -   **Password:** (deixe em branco)

3.  Clique em **Connect**. Você poderá ver a tabela `USERS` e os dados que foram cadastrados.
