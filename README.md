# 📚 Sistema de Biblioteca — API de Livros

> Projeto desenvolvido na disciplina de **SW-II · Sistemas Web II**
> **ETEC Professora Maria Cristina Medeiros**

---

## 🎯 Sobre o projeto

O **Sistema de Biblioteca** é um projeto desenvolvido de forma incremental com o objetivo de construir uma aplicação Web para **gerenciamento de livros**.

A aplicação será composta por uma **API REST desenvolvida com FastAPI**, um **banco de dados MySQL** e, nas etapas seguintes, uma interface Web utilizando **HTML, CSS e JavaScript**.

Durante o desenvolvimento serão aplicados conceitos de:

* 🐍 Desenvolvimento Web com Python
* ⚡ Criação de APIs REST com FastAPI
* 🗄️ Persistência de dados com MySQL
* 🔗 SQLAlchemy
* 🔄 Operações CRUD
* 📡 Requisições HTTP
* 📋 Manipulação de JSON
* 🌐 Integração entre Front End e Back End
* 📦 Versionamento com Git e GitHub

---

# 🛠️ Tecnologias

| Tecnologia                    | Utilização                             |
| ----------------------------- | -------------------------------------- |
| 🐍 **Python**                 | Linguagem principal                    |
| ⚡ **FastAPI**                 | Desenvolvimento da API REST            |
| 🗄️ **MySQL**                 | Banco de dados                         |
| 🔗 **SQLAlchemy**             | Comunicação entre Python e banco       |
| 🔌 **PyMySQL**                | Driver de conexão com MySQL            |
| ⚙️ **Pydantic Settings**      | Configuração por variáveis de ambiente |
| 🚀 **Uvicorn**                | Servidor ASGI                          |
| 🌐 **HTML, CSS e JavaScript** | Front End nas próximas etapas          |
| 📦 **Git e GitHub**           | Versionamento do projeto               |

---

# 🏗️ Arquitetura

A arquitetura planejada para o projeto é:

```text
┌──────────────────────────────┐
│          FRONT END           │
│      HTML + CSS + JS         │
│     (etapa futura)           │
└──────────────┬───────────────┘
               │
               │ HTTP / JSON
               ▼
┌──────────────────────────────┐
│           API REST           │
│           FastAPI            │
└──────────────┬───────────────┘
               │
               │ SQLAlchemy
               ▼
┌──────────────────────────────┐
│          DATABASE            │
│            MySQL             │
│       biblioteca_db          │
└──────────────────────────────┘
```

Atualmente o projeto encontra-se na implementação da **fundação da API e conexão com o banco de dados**.

---

# 📂 Estrutura atual do projeto

```text
api-livros/
│
├── app/
│   ├── __init__.py
│   ├── database.py
│   └── main.py
│
├── database/
│   └── biblioteca_db.sql
│
├── .gitignore
├── README.md
└── requirements.txt
```

### 📁 `app/`

Contém o código Python da aplicação.

* `main.py` → inicialização do FastAPI e endpoints
* `database.py` → configuração da conexão com o banco
* `__init__.py` → identifica `app` como pacote Python

### 📁 `database/`

Contém os arquivos relacionados ao banco de dados.

* `biblioteca_db.sql` → script SQL utilizado para criar o banco `biblioteca_db`

### 📄 `requirements.txt`

Contém as dependências Python necessárias para executar o projeto.

---

# 🚀 Etapas do projeto

O sistema será desenvolvido em **quatro etapas**.

---

## 🟢 Etapa 1 — Fundação

### Implementado

* ✅ Estrutura inicial do projeto
* ✅ Ambiente Python
* ✅ Dependências do projeto
* ✅ Banco de dados `biblioteca_db`
* ✅ Arquivo SQL para criação do banco
* ✅ Configuração da conexão com o MySQL
* ✅ Configuração por arquivo `.env`
* ✅ Aplicação FastAPI
* ✅ Endpoint de verificação da API
* ✅ Verificação da conexão com o banco

### Endpoint atual

```http
GET /health
```

Quando a aplicação e o banco estão funcionando corretamente, a resposta esperada é:

```json
{
  "status": "ok",
  "database": "connected"
}
```

O endpoint também executa uma consulta simples no banco:

```sql
SELECT 1
```

Dessa forma, a rota verifica não apenas se o FastAPI está funcionando, mas também se existe comunicação com o banco de dados.

---

## 🔵 Etapa 2 — Modelo e consultas

Nesta etapa será criada a entidade principal do sistema: **Livro**.

### Planejado

* ⬜ Criação do modelo `Livro`
* ⬜ Criação da tabela de livros
* ⬜ Criação dos schemas
* ⬜ Configuração das sessões do banco
* ⬜ Cadastro de livros
* ⬜ Listagem de livros

### Endpoints previstos

| Método | Endpoint  | Função            |
| ------ | --------- | ----------------- |
| `POST` | `/livros` | ➕ Cadastrar livro |
| `GET`  | `/livros` | 📚 Listar livros  |

---

## 🟠 Etapa 3 — CRUD completo

Nesta etapa serão implementadas todas as operações CRUD.

### Operações

* ➕ **Create** — Criar
* 🔎 **Read** — Consultar
* ✏️ **Update** — Atualizar
* 🗑️ **Delete** — Excluir

### Endpoints previstos

| Método   | Endpoint       | Função             |
| -------- | -------------- | ------------------ |
| `POST`   | `/livros`      | ➕ Cadastrar livro  |
| `GET`    | `/livros`      | 📚 Listar livros   |
| `GET`    | `/livros/{id}` | 🔎 Consultar livro |
| `PUT`    | `/livros/{id}` | ✏️ Atualizar livro |
| `DELETE` | `/livros/{id}` | 🗑️ Excluir livro  |

### Tratamento de erros

Também serão tratados casos como:

* ⚠️ Livro não encontrado
* ⚠️ ID inexistente
* ⚠️ Dados inválidos
* ⚠️ Campos obrigatórios não informados
* ⚠️ Falha de comunicação com o banco

---

## 🟣 Etapa 4 — Front End

Na última etapa será criada uma interface Web para consumir a API.

### Tecnologias previstas

* 🌐 HTML5
* 🎨 CSS3
* ⚡ JavaScript
* 🔌 Fetch API

### Funcionalidades

* ➕ Cadastro de livros
* 📚 Listagem de livros
* ✏️ Edição
* 🗑️ Exclusão

O JavaScript será responsável por realizar requisições HTTP para os endpoints disponibilizados pelo FastAPI.

---

# 🗄️ Banco de dados

O banco utilizado no projeto é:

```text
biblioteca_db
```

O repositório já possui o arquivo:

```text
database/biblioteca_db.sql
```

Esse arquivo contém o script necessário para criar o banco.

Atualmente a estrutura da tabela de livros ainda não foi implementada, pois isso será realizado na **Etapa 2**.

---

# ⚙️ Configuração do ambiente

## 1️⃣ Clonar o repositório

```bash
git clone https://github.com/KaioDK/api-livros.git
```

---

## 2️⃣ Entrar na pasta

```bash
cd api-livros
```

---

## 3️⃣ Criar o ambiente virtual

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
source venv/bin/activate
```

---

## 4️⃣ Instalar as dependências

```bash
pip install -r requirements.txt
```

As principais dependências utilizadas atualmente são:

* FastAPI
* Uvicorn
* SQLAlchemy
* PyMySQL
* Pydantic
* Pydantic Settings
* python-dotenv

---

# 🔐 Configuração do `.env`

As informações de acesso ao banco de dados **não são armazenadas diretamente no código**.

Crie um arquivo chamado:

```text
.env
```

na raiz do projeto.

Exemplo:

```env
db_user=root
db_password=
db_host=localhost
db_port=3306
db_name=biblioteca_db
```

Altere os valores de acordo com a configuração do seu MySQL.

> ⚠️ O arquivo `.env` está incluído no `.gitignore` e não deve ser enviado ao GitHub, pois pode conter informações privadas de acesso ao banco.

---

# 🗃️ Criando o banco de dados

O arquivo SQL necessário para a criação do banco está disponível em:

```text
database/biblioteca_db.sql
```

É possível importá-lo utilizando ferramentas como:

* phpMyAdmin
* MySQL Workbench
* Terminal MySQL

Também é possível criar o banco manualmente:

```sql
CREATE DATABASE IF NOT EXISTS biblioteca_db
DEFAULT CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;
```

---

# ▶️ Executando a API

Com o ambiente virtual ativado e a partir da **raiz do projeto**, execute:

```bash
uvicorn app.main:app --reload
```

O servidor será iniciado normalmente em:

```text
http://127.0.0.1:8000
```

---

# ❤️ Testando a conexão

Com a API executando, acesse:

```text
http://127.0.0.1:8000/health
```

Resposta esperada:

```json
{
  "status": "ok",
  "database": "connected"
}
```

Caso essa resposta seja exibida, significa que:

```text
FastAPI
   │
   ▼
SQLAlchemy
   │
   ▼
PyMySQL
   │
   ▼
MySQL
```

estão conseguindo se comunicar corretamente.

---

# 📖 Swagger UI

O FastAPI gera automaticamente uma interface para visualizar e testar os endpoints.

Acesse:

```text
http://127.0.0.1:8000/docs
```

Na etapa atual estará disponível principalmente o endpoint:

```http
GET /health
```

---

# 📘 ReDoc

Outra documentação automática disponibilizada pelo FastAPI pode ser acessada em:

```text
http://127.0.0.1:8000/redoc
```

---

# 📈 Progresso

| Etapa      | Status         | Resultado                    |
| ---------- | -------------- | ---------------------------- |
| 🟢 Etapa 1 | ✅ Implementada | Fundação e conexão com banco |
| 🔵 Etapa 2 | ⬜ Pendente     | Modelo e consultas           |
| 🟠 Etapa 3 | ⬜ Pendente     | CRUD completo                |
| 🟣 Etapa 4 | ⬜ Pendente     | Front End                    |

```text
Etapa 1  ██████████  Fundação
Etapa 2  ░░░░░░░░░░  Modelo e consultas
Etapa 3  ░░░░░░░░░░  CRUD completo
Etapa 4  ░░░░░░░░░░  Front End
```

---

# 🔮 Estrutura prevista

Conforme o projeto evoluir, novos arquivos e diretórios poderão ser adicionados.

Uma possível evolução é:

```text
api-livros/
│
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── database.py
│   ├── models.py
│   ├── schemas.py
│   │
│   └── routers/
│       └── livros.py
│
├── database/
│   └── biblioteca_db.sql
│
├── frontend/
│   ├── index.html
│   ├── style.css
│   └── script.js
│
├── .gitignore
├── requirements.txt
└── README.md
```

> Essa é apenas uma previsão. A estrutura deverá ser atualizada conforme as próximas etapas forem realmente implementadas.

---

# 🧪 Testes

Durante o desenvolvimento poderão ser utilizadas ferramentas como:

* 🔵 Swagger UI
* 📮 Postman
* 🌐 Navegador
* 💻 Front End da aplicação
* 🧪 Testes automatizados

Os testes serão adicionados progressivamente de acordo com a evolução da API.

---

# 🎓 Objetivos educacionais

O projeto permite aplicar na prática:

* Desenvolvimento de aplicações Web com Python
* Construção de APIs REST
* Utilização do FastAPI
* Conexão com banco de dados
* Utilização do SQLAlchemy
* Manipulação de dados JSON
* Requisições HTTP
* Operações CRUD
* Organização de projetos
* Integração Front End e Back End
* Testes de API
* Versionamento com Git e GitHub

---

# 👨‍💻 Disciplina

**SW-II · Sistemas Web II**

**ETEC Professora Maria Cristina Medeiros**

Projeto desenvolvido com finalidade **didática e educacional**, acompanhando de forma incremental as etapas de construção de uma aplicação Web.

---

## ⭐ Proposta

> **Do banco de dados à interface Web: construindo uma aplicação completa passo a passo.**

O objetivo é compreender não apenas como cada tecnologia funciona individualmente, mas também como **API, banco de dados e interface Web se comunicam dentro de uma aplicação completa**.

---

## 📌 Status

🚧 **Projeto em desenvolvimento**

**Etapa atual: 🟢 Fundação da aplicação**
