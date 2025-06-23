# User Management API

API feita em NestJS e PostgreSQL para cadastro, login e gerenciamento de usuários.  
A documentação dos endpoints é automática pelo Swagger.

---

## O que esse projeto faz?

- Permite criar contas de usuário
- Faz login e retorna um token JWT para autenticação
- Permite atualizar dados do usuário
- Guarda tudo em um banco de dados Postgres

---

## O que você precisa para rodar

- Node.js
- PostgreSQL instalado, rodando e com um banco criado
- Um arquivo `.env` configurado (veja abaixo)

---

## Como rodar o projeto

1. Clone este repositório e entre na pasta:

   ```bash
   git clone <URL_DO_REPOSITORIO>
   cd <PASTA_DO_PROJETO>
   ```

2. Instale as dependências:

   ```bash
   npm install
   ```

3. Crie um banco de dados no Postgres (pode ser pelo terminal ou algum client):

   ```bash
   createdb user_management
   ```

4. Crie um arquivo `.env` na raiz do projeto com essas informações (troque pelos seus dados):

   ```
   JWT_SECRET=sua_chave_secreta
   DB_HOST=localhost
   DB_PORT=5432
   DB_USERNAME=seu_usuario
   DB_PASSWORD=sua_senha
   DB_DATABASE=user_management
   ```

5. Inicie o servidor:

   ```bash
   npm run start:dev
   ```

6. Você pode acessar a documentação Swagger em:
   [http://localhost:3000/api](http://localhost:3000/api)

---

## Sobre o banco de dados

O projeto usa Postgres. Os dados de conexão vêm do arquivo `.env`, então você pode mudar o nome do banco, usuário e senha conforme sua máquina.

---

## Documentação automática

Assim que o servidor sobe, o Swagger fica disponível em `/api`, mostrando todos os endpoints, exemplos de requisição/resposta e os modelos de dados (schemas).

---

## Principais endpoints

- `POST /auth/register` — cria usuário
- `POST /auth/login` — login e retorna um token JWT
- `GET /users` — lista usuários (precisa de token)
- `GET /users/:id` — detalhes do usuário (precisa de token)
- `PUT /users/:id` — atualiza usuário (precisa de token)

---

## Dicas

- Se der erro de conexão no banco, confira se o Postgres está rodando e se o `.env` está certo.
- Se não aparecer nada nos schemas do Swagger, veja se os DTOs têm o decorator `@ApiProperty`.
- Sempre proteja seu arquivo `.env` (não envie para o GitHub).

--
