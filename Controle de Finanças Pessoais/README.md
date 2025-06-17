# 💰 App de Controle de Finanças Pessoais

Aplicativo fullstack para ajudar usuários a controlar suas receitas e despesas mensais, visualizar gráficos e receber alertas de orçamento.

---

## 🛠️ Tecnologias Utilizadas

### 🔙 Backend
- Java 17
- Spring Boot
- Spring Security + JWT
- Spring Data JPA
- PostgreSQL

### 📱 Frontend
- React Native (com Expo)
- React Navigation
- Axios
- Victory Native (para gráficos)
- AsyncStorage

---

## 🧩 Funcionalidades

- ✅ Cadastro e login de usuário
- ➕ Registro de receitas e despesas
- 📂 Categorias personalizadas (Alimentação, Lazer, Transporte etc.)
- 📊 Gráficos mensais de gastos
- ⚠️ Alerta de orçamento estourado (meta mensal)

---

## 📐 Estrutura do Banco de Dados

```sql
usuarios (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(100),
  email VARCHAR(150) UNIQUE,
  senha VARCHAR(255)
)

categorias (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(100),
  tipo VARCHAR(10), -- 'RECEITA' ou 'DESPESA'
  id_usuario INTEGER REFERENCES usuarios(id)
)

transacoes (
  id SERIAL PRIMARY KEY,
  valor DECIMAL(10,2),
  descricao TEXT,
  data DATE,
  tipo VARCHAR(10), -- 'RECEITA' ou 'DESPESA'
  id_categoria INTEGER REFERENCES categorias(id),
  id_usuario INTEGER REFERENCES usuarios(id)
)

metas (
  id SERIAL PRIMARY KEY,
  valor_mensal DECIMAL(10,2),
  mes INTEGER,
  ano INTEGER,
  id_usuario INTEGER REFERENCES usuarios(id)
)
````

---

## 🔌 Principais Rotas da API

| Método | Rota             | Descrição                    |
| ------ | ---------------- | ---------------------------- |
| POST   | `/auth/register` | Cadastro de usuário          |
| POST   | `/auth/login`    | Login e geração do token JWT |
| GET    | `/transacoes`    | Listar transações do mês     |
| POST   | `/transacoes`    | Criar nova transação         |
| GET    | `/categorias`    | Listar categorias            |
| POST   | `/categorias`    | Criar nova categoria         |
| GET    | `/metas`         | Buscar meta atual            |
| POST   | `/metas`         | Criar/atualizar meta do mês  |

---

## 📱 Sugestões de Telas no App

1. **Tela de Login / Registro**
2. **Dashboard**

   * Gráfico de gastos vs receitas
   * Total do mês
   * Meta do mês
3. **Lista de Transações**

   * Filtro por data e tipo
4. **Adicionar Transação**

   * Campo de valor, descrição, data, categoria
5. **Categorias**

   * Criar e listar
6. **Configurar Meta Mensal**

---

## 🚀 Como Executar

**Backend**

```bash
cd backend
./mvnw spring-boot:run
```

**Frontend**

```bash
cd app
npm install
npx expo start
```

---

## ✍️ Autor

João Gabriel – Estudante de ADS (FIAP)

```

---

Se quiser, posso agora:
- gerar o **esqueleto do projeto Spring Boot** com classes `User`, `Categoria`, `Transacao`
- ou criar as **telas base em React Native com navegação**

Qual parte você quer montar primeiro? Backend, app ou banco?
```
