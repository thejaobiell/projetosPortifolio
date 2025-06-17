# 📅 Sistema de Agendamento de Serviços

Projeto FullStack com **Java Spring Boot (backend)**, **React Native (frontend mobile)** e **PostgreSQL (banco de dados)**.

Este aplicativo permite que usuários agendem serviços com profissionais em horários disponíveis, com autenticação segura, gerenciamento de horários e histórico de agendamentos.

---

## 🛠️ Tecnologias Utilizadas

### 📦 Backend
- Java 17
- Spring Boot
- Spring Security + JWT
- Spring Data JPA
- PostgreSQL
- Swagger (Documentação da API)

### 📱 Frontend
- React Native (com Expo)
- React Navigation
- Axios (requisições HTTP)
- AsyncStorage (armazenamento local de token)

### 🗄️ Banco de Dados
- MySQL

---

## 📐 Estrutura do Projeto

```

/backend        -> Projeto Spring Boot (Java)
/app            -> Aplicativo mobile em React Native
/database       -> Scripts SQL ou configurações do banco

````

---

## 🚀 Funcionalidades

### 👤 Autenticação
- Cadastro e login de usuários (JWT)
- Tipos de usuário: Cliente ou Profissional

### 📋 Serviços
- Listagem de serviços cadastrados
- Visualização de detalhes

### 📆 Agendamentos
- Cliente agenda um horário com profissional
- Profissional define horários disponíveis
- Cancelamento e histórico de agendamentos

---

## ⚙️ Como Executar o Projeto

### 🔙 Backend

1. Acesse a pasta `backend`:
   ```bash
   cd backend
  ```

2. Configure o `application.properties`:

   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/agendamentos
   spring.datasource.username=seu_usuario
   spring.datasource.password=sua_senha
   ```

3. Rode a aplicação:

   ```bash
   ./mvnw spring-boot:run
   ```

4. Acesse a API em: `http://localhost:8080`

5. Swagger (documentação): `http://localhost:8080/swagger-ui.html`

---

### 📱 Frontend

1. Acesse a pasta `app`:

   ```bash
   cd app
   ```

2. Instale as dependências:

   ```bash
   npm install
   ```

3. Inicie com Expo:

   ```bash
   npx expo start
   ```

4. Escaneie o QR code com o app Expo Go para rodar no celular (ou use emulador)

---

## 🗃️ Banco de Dados

Modelo inicial:

```
usuarios (id, nome, email, senha, tipo)
servicos (id, nome, descricao, duracao, preco)
disponibilidade (id, id_user, data, hora_inicio, hora_fim)
horarios (id, id_user, id_service, data, hora, status)
```

---

## ✅ Status do Projeto

* [x] Estrutura inicial backend com Spring Boot
* [x] Autenticação com JWT
* [x] CRUD de usuários e serviços
* [x] Agendamento de horários
* [x] Integração com frontend

---

## ✍️ Autor

João Gabriel
Estudante de Análise e Desenvolvimento de Sistemas – FIAP
GitHub: [github.com/thejaobiell](https://github.com/thejaobiell)
LinkedIn: [www.linkedin.com/in/joao-gabriel-b-93b67b323](www.linkedin.com/in/joao-gabriel-b-93b67b323)
