
# ✅ To-Do List API com Laravel

API RESTful completa para gerenciamento de tarefas, com autenticação segura via Laravel Sanctum. Desenvolvida com foco em segurança, boas práticas e pronta para deploy.

## 🚀 Funcionalidades

- Cadastro e login de usuários
- Autenticação via token (Bearer Token - Sanctum)
- CRUD de tarefas (To-do)
- Associação de tarefas ao usuário autenticado
- Validação, tratamento de erros e segurança

## 🔧 Tecnologias

- Laravel 11+
- Sanctum (autenticação API)
- MySQL ou SQLite
- PHP 8.1+
- Postman/Insomnia para testes

## 📦 Instalação local

```bash
git clone https://github.com/RafaelVitorSantos/todo-api-laravel.git
cd todo-api-laravel
composer install
cp .env.example .env
php artisan key:generate
```

Configure o banco de dados no arquivo `.env`. Exemplo com MySQL:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=todo_api
DB_USERNAME=root
DB_PASSWORD=
```

Depois, execute:

```bash
php artisan migrate
php artisan serve
```

## 🔐 Autenticação

- Utilize o endpoint `/api/register` para criar uma conta
- Faça login em `/api/login` e copie o `token` de acesso
- Use o token nos headers das requisições:

```
Authorization: Bearer SEU_TOKEN
```

## 🧪 Testes com Postman / Insomnia

### 📌 Registro

**POST** `/api/register`

```json
{
  "name": "Rafael",
  "email": "rafael@email.com",
  "password": "senha123",
  "password_confirmation": "senha123"
}
```

### 🔐 Login

**POST** `/api/login`

```json
{
  "email": "rafael@email.com",
  "password": "senha123"
}
```

### 📋 Listar tarefas

**GET** `/api/tasks`

### ➕ Criar tarefa

**POST** `/api/tasks`

```json
{
  "title": "Estudar Laravel",
  "description": "Implementar o CRUD"
}
```

### ✏️ Atualizar tarefa

**PUT** `/api/tasks/1`

```json
{
  "title": "Estudar Laravel atualizado",
  "completed": true
}
```

### ❌ Deletar tarefa

**DELETE** `/api/tasks/1`

## ✅ Usando SQLite (opcional)

Configure no `.env`:

```env
DB_CONNECTION=sqlite
DB_DATABASE=./database/database.sqlite
```

Crie o arquivo do banco:

```bash
touch database/database.sqlite
php artisan migrate
```

## 📄 Licença

Este projeto está sob a licença MIT. Livre para usar e contribuir.

## 💼 Autor

Feito por Rafael Santos (https://www.linkedin.com/in/rafaelvitorsantos/)
