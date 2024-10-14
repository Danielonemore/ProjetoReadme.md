# Projeto PetLife - Backend (trabalho-api)

## Descrição

O sistema PetLife é um Sistema de Gerenciamento de Clínica Veterinária, desenvolvido para simplificar e otimizar as operações diárias de clínicas veterinárias. O backend é responsável por gerenciar as informações de animais, proprietários e funcionários, além de controlar agendamentos e visualizar históricos médicos dos animais. A aplicação visa melhorar a eficiência e a qualidade do atendimento veterinário.

## Tecnologias Utilizadas

- Java 17
- Spring Boot
- PostgreSQL
- Maven

## Pré-requisitos

- JDK 17
- Maven 3.8.1+
- PostgreSQL

## Instalação

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/Danielonemore/ProjetoReadme.md/tree/main/trabalho-api-main
   ```

2. **Navegue até o diretório do projeto:**

   ```bash
   cd diretorio-do-projeto
   ```

3. **Configure o banco de dados:**

   Edite o arquivo [application.yaml](src/main/resources/application.yaml) com as configurações do seu banco de dados.

4. **Compile e execute o projeto:**

   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

   A API estará disponível em `http://localhost:8080`.

## Documentação da API (Swagger)

A documentação da API pode ser acessada por meio do Swagger. Após iniciar o backend, você pode acessar a documentação por meio da seguinte URL:

[/swagger-ui/index.html](http://localhost:8080//swagger-ui/index.html)

## Endpoints

Abaixo está a descrição dos principais endpoints da API:

{Alterar os endpoints conforme os endpoints do projeto}

### **1. GET /api/usuarios**

- **Descrição:** Retorna uma lista de usuários.
- **Parâmetros de Consulta:**
  - `page` (opcional): Número da página.
  - `size` (opcional): Número de itens por página.
- **Resposta:**
  - **200 OK**
    ```json
    [
      {
        "id": 1,
        "nome": "João",
        "email": "joao@exemplo.com"
      },
      // ...
    ]
    ```

### **2. POST /api/usuarios**

- **Descrição:** Cria um novo usuário.
- **Corpo da Requisição:**
  ```json
  {
    "nome": "Maria",
    "email": "maria@exemplo.com"
  }
  ```
- **Resposta:**
  - **201 Created**
    ```json
    {
      "id": 2,
      "nome": "Maria",
      "email": "maria@exemplo.com"
    }
    ```

### **3. GET /api/usuarios/{id}**

- **Descrição:** Retorna um usuário específico pelo ID.
- **Parâmetros de Caminho:**
  - `id`: ID do usuário.
- **Resposta:**
  - **200 OK**
    ```json
    {
      "id": 1,
      "nome": "João",
      "email": "joao@exemplo.com"
    }
    ```
  - **404 Not Found** (se o usuário não for encontrado)

### **4. PUT /api/usuarios/{id}**

- **Descrição:** Atualiza um usuário existente.
- **Corpo da Requisição:**
  ```json
  {
    "nome": "João Atualizado",
    "email": "joaoatualizado@exemplo.com"
  }
  ```
- **Parâmetros de Caminho:**
  - `id`: ID do usuário.
- **Resposta:**
  - **200 OK**
    ```json
    {
      "id": 1,
      "nome": "João Atualizado",
      "email": "joaoatualizado@exemplo.com"
    }
    ```
  - **404 Not Found** (se o usuário não for encontrado)

### **5. DELETE /api/usuarios/{id}**

- **Descrição:** Remove um usuário pelo ID.

- **Parâmetros de Caminho:**
  - `id`: ID do usuário.
- **Resposta:**
  - **204 No Content**
  - **404 Not Found** (se o usuário não for encontrado)

### **1. GET /api/animais**

- **Descrição:** Retorna uma lista de animais cadastrados.

- **Parâmetros de Consulta:**
  - `page` (opcional): Número da página.
  - `size` (opcional): Número de itens por página.
- **Resposta:**
  - **200 OK**
    ```json
    [
      {
        "id": 1,
        "nome": "Bobby",
        "especie": "Cão"
      },
      // ...
    ]
    ```
### **2. POST /api/animais**

 **Descrição:** Cria um novo registro de animal.
- **Corpo da Requisição:**
  ```json
  {
    "nome": "Rex",
    "especie": "Cão",
    "idade": 3,
    "proprietarioId": 1
  }
  ```
- **Resposta:**
  - **201 Created**
    ```json
    {
       "id": 2,
       "nome": "Rex",
       "especie": "Cão",
       "idade": 3,
       "proprietarioId": 1
    }
    ```
### **3. GET /api/animais/{id}**

- **Descrição:** Retorna um animal específico pelo ID.

- **Parâmetros de Caminho:**
  - `id`: ID do animal.
- **Resposta:**
  - **200 OK**
    ```json
    {
      "id": 1,
      "nome": "Bobby",
      "especie": "Cão"
    }
    ```
  - **404 Not Found** (se o animal não for encontrado)

### **4. PUT /api/animais/{id}**

- **Descrição:**  Atualiza as informações de um animal existente.

- **Corpo da Requisição:**
  ```json
  {
    "nome": "Bobby Atualizado",
    "especie": "Cão"
  }
  ```
- **Parâmetros de Caminho:**
  - `id`: ID do animal.
- **Resposta:**
  - **200 OK**
    ```json
    {
      "id": 1,
      "nome": "Bobby Atualizado",
      "especie": "Cão"
    }
    ```
  - **404 Not Found** (se o animal não for encontrado)

### **5. DELETE /api/animais/{id}**

- **Descrição:** Remove um animal pelo ID.

- **Parâmetros de Caminho:**
  - `id`: ID do animal.
- **Resposta:**
  - **204 No Content**
  - **404 Not Found** (se o animal não for encontrado)