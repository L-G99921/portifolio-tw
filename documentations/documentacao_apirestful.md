# Documentação de API RESTful

Bem-vindo à documentação da API RESTful! Esta documentação fornece detalhes sobre como interagir com a API, incluindo endpoints, métodos HTTP suportados, parâmetros e exemplos de respostas.

## Sumário
- [Introdução](#introdução)
- [Autenticação](#autenticação)
- [Endpoints](#endpoints)
  - [Usuários](#usuários)
    - [Obter Usuários](#obter-usuários)
    - [Criar Usuário](#criar-usuário)
    - [Obter Usuário por ID](#obter-usuário-por-id)
    - [Atualizar Usuário](#atualizar-usuário)
    - [Excluir Usuário](#excluir-usuário)
  - [Projetos](#projetos)
    - [Obter Projetos](#obter-projetos)
    - [Criar Projeto](#criar-projeto)
    - [Obter Projeto por ID](#obter-projeto-por-id)
    - [Atualizar Projeto](#atualizar-projeto)
    - [Excluir Projeto](#excluir-projeto)
- [Erros Comuns](#erros-comuns)
- [Recursos Adicionais](#recursos-adicionais)

## Introdução
Esta API RESTful permite gerenciar usuários e projetos em uma aplicação de gestão de projetos. A API segue os padrões REST, utilizando métodos HTTP para as operações CRUD (Create, Read, Update, Delete).

## Autenticação
Para utilizar a API, é necessário autenticar-se utilizando tokens JWT (JSON Web Tokens).

> ℹ️ **Nota:** Inclua o token de autenticação no cabeçalho de cada requisição:
> ```
> Authorization: Bearer <seu-token-jwt>
> ```

## Endpoints

### Usuários

#### Obter Usuários
- **Endpoint:** `/api/users`
- **Método:** `GET`
- **Descrição:** Retorna a lista de todos os usuários.
- **Resposta de Sucesso:**
  ```json
  [
    {
      "id": 1,
      "nome": "João Silva",
      "email": "joao.silva@example.com"
    },
    {
      "id": 2,
      "nome": "Maria Souza",
      "email": "maria.souza@example.com"
    }
  ]
  ```

#### Criar Usuário
- **Endpoint:** `/api/users`
- **Método:** `POST`
- **Descrição:** Cria um novo usuário.
- **Corpo da Requisição:**
  ```json
  {
    "nome": "João Silva",
    "email": "joao.silva@example.com",
    "senha": "senha123"
  }
  ```
- **Resposta de Sucesso:**
  ```json
  {
    "id": 1,
    "nome": "João Silva",
    "email": "joao.silva@example.com"
  }
  ```

#### Obter Usuário por ID
- **Endpoint:** `/api/users/{id}`
- **Método:** `GET`
- **Descrição:** Retorna os detalhes de um usuário específico.
- **Parâmetros da URL:**
  - `id` (obrigatório): ID do usuário
- **Resposta de Sucesso:**
  ```json
  {
    "id": 1,
    "nome": "João Silva",
    "email": "joao.silva@example.com"
  }
  ```

#### Atualizar Usuário
- **Endpoint:** `/api/users/{id}`
- **Método:** `PUT`
- **Descrição:** Atualiza as informações de um usuário específico.
- **Parâmetros da URL:**
  - `id` (obrigatório): ID do usuário
- **Corpo da Requisição:**
  ```json
  {
    "nome": "João Silva",
    "email": "joao.silva@example.com",
    "senha": "novaSenha123"
  }
  ```
- **Resposta de Sucesso:**
  ```json
  {
    "id": 1,
    "nome": "João Silva",
    "email": "joao.silva@example.com"
  }
  ```

#### Excluir Usuário
- **Endpoint:** `/api/users/{id}`
- **Método:** `DELETE`
- **Descrição:** Exclui um usuário específico.
- **Parâmetros da URL:**
  - `id` (obrigatório): ID do usuário
- **Resposta de Sucesso:**
  ```json
  {
    "mensagem": "Usuário excluído com sucesso"
  }
  ```

### Projetos

#### Obter Projetos
- **Endpoint:** `/api/projects`
- **Método:** `GET`
- **Descrição:** Retorna a lista de todos os projetos.
- **Resposta de Sucesso:**
  ```json
  [
    {
      "id": 1,
      "nome": "Projeto A",
      "descricao": "Descrição do Projeto A"
    },
    {
      "id": 2,
      "nome": "Projeto B",
      "descricao": "Descrição do Projeto B"
    }
  ]
  ```

#### Criar Projeto
- **Endpoint:** `/api/projects`
- **Método:** `POST`
- **Descrição:** Cria um novo projeto.
- **Corpo da Requisição:**
  ```json
  {
    "nome": "Projeto A",
    "descricao": "Descrição do Projeto A"
  }
  ```
- **Resposta de Sucesso:**
  ```json
  {
    "id": 1,
    "nome": "Projeto A",
    "descricao": "Descrição do Projeto A"
  }
  ```

#### Obter Projeto por ID
- **Endpoint:** `/api/projects/{id}`
- **Método:** `GET`
- **Descrição:** Retorna os detalhes de um projeto específico.
- **Parâmetros da URL:**
  - `id` (obrigatório): ID do projeto
- **Resposta de Sucesso:**
  ```json
  {
    "id": 1,
    "nome": "Projeto A",
    "descricao": "Descrição do Projeto A"
  }
  ```

#### Atualizar Projeto
- **Endpoint:** `/api/projects/{id}`
- **Método:** `PUT`
- **Descrição:** Atualiza as informações de um projeto específico.
- **Parâmetros da URL:**
  - `id` (obrigatório): ID do projeto
- **Corpo da Requisição:**
  ```json
  {
    "nome": "Projeto A",
    "descricao": "Descrição atualizada do Projeto A"
  }
  ```
- **Resposta de Sucesso:**
  ```json
  {
    "id": 1,
    "nome": "Projeto A",
    "descricao": "Descrição atualizada do Projeto A"
  }
  ```

#### Excluir Projeto
- **Endpoint:** `/api/projects/{id}`
- **Método:** `DELETE`
- **Descrição:** Exclui um projeto específico.
- **Parâmetros da URL:**
  - `id` (obrigatório): ID do projeto
- **Resposta de Sucesso:**
  ```json
  {
    "mensagem": "Projeto excluído com sucesso"
  }
  ```

## Erros Comuns
### 400 Bad Request
- **Descrição:** A requisição contém parâmetros inválidos ou está malformada.
- **Exemplo de Resposta:**
  ```json
  {
    "erro": "Requisição inválida. Verifique os parâmetros e tente novamente."
  }
  ```

### 401 Unauthorized
- **Descrição:** A requisição não contém um token de autenticação válido.
- **Exemplo de Resposta:**
  ```json
  {
    "erro": "Autenticação necessária. Por favor, forneça um token válido."
  }
  ```

### 404 Not Found
- **Descrição:** O recurso solicitado não foi encontrado.
- **Exemplo de Resposta:**
  ```json
  {
    "erro": "Recurso não encontrado."
  }
  ```

### 500 Internal Server Error
- **Descrição:** Ocorreu um erro no servidor.
- **Exemplo de Resposta:**
  ```json
  {
    "erro": "Erro interno do servidor. Tente novamente mais tarde."
  }
  ```

## Recursos Adicionais
- [Guia de Autenticação](#)
- [Documentação Completa da API](#)
- [Exemplos de Uso da API](#)

---

Esperamos que esta documentação ajude você a integrar e utilizar nossa API RESTful de maneira eficaz. Se tiver qualquer dúvida ou precisar de assistência adicional, não hesite em entrar em contato conosco.

Boas integrações!