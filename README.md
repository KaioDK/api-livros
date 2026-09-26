# 📚 Sistema de Biblioteca

> Projeto desenvolvido na disciplina de **SW-II · Sistemas Web II**  
> **ETEC Professora Maria Cristina Medeiros**

---

## 🎯 Sobre o projeto

O **Sistema de Biblioteca** é uma aplicação Web desenvolvida para o gerenciamento de livros.

O projeto utiliza uma arquitetura composta por **API REST, banco de dados e Front End**, permitindo cadastrar, consultar, editar e excluir livros.

---

## 🛠️ Tecnologias utilizadas

| Camada | Tecnologia |
|---|---|
| ⚙️ Back End | **FastAPI** |
| 🐍 Linguagem | **Python** |
| 🗄️ Banco de Dados | **MySQL / MariaDB** |
| 🔗 ORM | **SQLAlchemy** |
| 🌐 Front End | **HTML5 + CSS3 + JavaScript** |
| 🔌 Comunicação | **API REST / Fetch API** |
| 📦 Versionamento | **Git e GitHub** |

---

## 🏗️ Arquitetura

```text
┌─────────────────────┐
│      FRONT END      │
│   HTML + CSS + JS   │
└──────────┬──────────┘
           │ HTTP / JSON
           ▼
┌─────────────────────┐
│      API REST       │
│       FastAPI       │
└──────────┬──────────┘
           │ SQLAlchemy
           ▼
┌─────────────────────┐
│      DATABASE       │
│    MySQL/MariaDB    │
└─────────────────────┘
```

---

# 📂 Estrutura do projeto

```text
api-livros/
│
├── app/
│   ├── __init__.py
│   ├── database.py
│   ├── main.py
│   ├── models.py
│   └── schemas.py
│
├── database/
│   └── biblioteca_db.sql
│
├── frontend/
│   ├── index.html
│   ├── app.js
│   └── styles.css
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

# 🗃️ Banco de dados

O projeto utiliza o banco:

```text
biblioteca_db
```

A entidade principal é `Livro`, contendo os campos:

| Campo | Descrição |
|---|---|
| `id` | Identificador do livro |
| `titulo` | Título |
| `autor` | Autor |
| `ano_publicacao` | Ano de publicação |
| `disponivel` | Disponibilidade |

Exemplo:

```json
{
  "titulo": "Dom Casmurro",
  "autor": "Machado de Assis",
  "ano_publicacao": 1899,
  "disponivel": true
}
```

---

# 🔌 API REST

A API possui as operações principais de um CRUD.

| Método | Endpoint | Função |
|---|---|---|
| `POST` | `/livros` | ➕ Cadastrar livro |
| `GET` | `/livros` | 📚 Listar livros |
| `GET` | `/livros/{id_livro}` | 🔎 Consultar livro |
| `PUT` | `/livros/{id_livro}` | ✏️ Atualizar livro |
| `DELETE` | `/livros/{id_livro}` | 🗑️ Excluir livro |

Também existem tratamentos para situações como:

- Livro não encontrado
- ID inexistente
- Dados inválidos
- Campos obrigatórios não informados

---

# 🌐 Front End

O Front End foi desenvolvido utilizando:

- HTML5
- CSS3
- JavaScript
- Fetch API

A interface permite:

- ➕ Cadastrar livros
- 📚 Listar livros
- ✏️ Editar livros
- 🗑️ Excluir livros
- ✅ Visualizar a disponibilidade

O JavaScript se comunica com a API FastAPI através de requisições HTTP.

---

# ⚙️ Instalação

## 1️⃣ Clonar o repositório

```bash
git clone https://github.com/KaioDK/api-livros.git
```

## 2️⃣ Entrar na pasta

```bash
cd api-livros
```

## 3️⃣ Criar o ambiente virtual

```bash
python -m venv .venv
```

### Windows PowerShell

```powershell
.\.venv\Scripts\Activate.ps1
```

### Linux / macOS

```bash
source .venv/bin/activate
```

## 4️⃣ Instalar as dependências

```bash
pip install -r requirements.txt
```

---

# 🔐 Configuração do banco

Crie um arquivo `.env` na raiz do projeto:

```env
db_user=root
db_password=
db_host=localhost
db_port=3306
db_name=biblioteca_db
```

Altere os valores conforme a configuração do seu MySQL/MariaDB.

O arquivo `.env` não deve ser enviado para o GitHub.

O script do banco está disponível em:

```text
database/biblioteca_db.sql
```

---

# ▶️ Executando a API

Na raiz do projeto:

```bash
uvicorn app.main:app --reload
```

A API ficará disponível em:

```text
http://127.0.0.1:8000
```

### Swagger UI

```text
http://127.0.0.1:8000/docs
```

### ReDoc

```text
http://127.0.0.1:8000/redoc
```

---

# 🖥️ Executando o Front End

O Front End deve ser executado por um servidor local.

Utilizando Python:

```bash
python -m http.server 5500 --directory frontend
```

Depois acesse:

```text
http://127.0.0.1:5500
```

O projeto também possui configuração de CORS permitindo a comunicação entre o Front End na porta `5500` e a API na porta `8000`.

---

# 🚀 Etapas do projeto

## 🟢 Etapa 1 — Fundação

- ✅ Configuração do ambiente
- ✅ Banco de dados
- ✅ Conexão com MySQL
- ✅ Configuração do FastAPI

## 🔵 Etapa 2 — Modelo e consultas

- ✅ Modelo `Livro`
- ✅ Schemas
- ✅ Cadastro de livros
- ✅ Listagem de livros

## 🟠 Etapa 3 — CRUD completo

- ✅ Criar
- ✅ Consultar
- ✅ Atualizar
- ✅ Excluir
- ✅ Tratamento de erros

## 🟣 Etapa 4 — Front End

- ✅ HTML
- ✅ CSS
- ✅ JavaScript
- ✅ Fetch API
- ✅ Integração com a API

---

# 📈 Progresso

| Etapa | Status |
|---|---|
| 🟢 Etapa 1 | ✅ Concluída |
| 🔵 Etapa 2 | ✅ Concluída |
| 🟠 Etapa 3 | ✅ Concluída |
| 🟣 Etapa 4 | ✅ Concluída |

---

# 🎓 Objetivos educacionais

Durante o desenvolvimento foram trabalhados conceitos de:

- Desenvolvimento Web com Python
- APIs REST com FastAPI
- Banco de dados MySQL
- SQLAlchemy
- Operações CRUD
- Requisições HTTP
- Manipulação de JSON
- HTML, CSS e JavaScript
- Fetch API
- Integração entre Front End e Back End
- Git e GitHub

---

# 👨‍💻 Disciplina

**SW-II · Sistemas Web II**

**ETEC Professora Maria Cristina Medeiros**

Projeto desenvolvido com finalidade **didática e educacional**.

---

## ⭐ Proposta

> **Do banco de dados à interface Web: construindo uma aplicação completa passo a passo.**

---

## 📌 Status

✅ **CRUD completo**  
✅ **Banco de dados integrado**  
✅ **Front End integrado à API**
