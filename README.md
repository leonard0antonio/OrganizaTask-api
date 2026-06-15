# ⚙️ OrganizaTask API (Back-end)

![Demo da aplicação](demo.png)


![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Express](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)
![Prisma](https://img.shields.io/badge/Prisma-3982CE?style=for-the-badge&logo=Prisma&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)

---

## 🎯 Arquitetura e Funcionalidades Principais

* **Arquitetura Multi-Tenant:** Isolamento absoluto de dados. Membros só têm acesso às tarefas e times do Workspace do qual fazem parte.
* **Autenticação Segura:** Autenticação via JWT (JSON Web Tokens) com senhas criptografadas via bcrypt.
* **Controle de Acesso (RBAC):**
  * `Admin`: Gestão total do Workspace, criação de times, registro de membros e visão global das demandas.
  * `Member`: Visão isolada, com acesso exclusivo às tarefas atribuídas a si ou abertas para o seu Squad.
* **ORM Moderno:** Utilização do Prisma ORM para queries tipadas, seguras e migrações ágeis.

---

## 📊 Modelo Entidade-Relacionamento (MER)

Abaixo está a representação da arquitetura de banco de dados do projeto, destacando o auto-relacionamento da tabela `User` que viabiliza a regra de negócio do Workspace.

```mermaid
erDiagram
    USER ||--o{ USER : "gerencia (adminId)"
    USER ||--o{ TASK : "é responsável por (assigned_to)"
    USER ||--o{ TASK : "cria para o workspace (adminId)"
    TEAM ||--o{ TASK : "possui (team_id)"
    
    USER {
        int id PK
        string name
        string email
        string password
        string role "admin | member"
        int adminId FK "Nullable (Auto-relacionamento)"
        datetime created_at
    }
    
    TEAM {
        int id PK
        string name
        datetime created_at
    }
    
    TASK {
        int id PK
        string title
        string description
        string priority "high | medium | low"
        string status "pending | in_progress | completed"
        int adminId FK "Workspace Link"
        int team_id FK
        int assigned_to FK "Nullable"
        datetime created_at
    }

```

---

## 🚀 Como executar o projeto localmente

### Pré-requisitos

* Node.js v18+
* Instância do PostgreSQL (Local ou Nuvem via Supabase)

### Instalação

1. Clone este repositório:

```bash
git clone [https://github.com/leonard0antonio/task-manager-api.git](https://github.com/leonard0antonio/task-manager-api.git)

```

2. Acesse o diretório e instale as dependências:

```bash
cd task-manager-api
npm install

```

3. Configure as variáveis de ambiente em um arquivo `.env` na raiz do projeto:

```env
DATABASE_URL="postgresql://usuario:senha@localhost:5432/organizatask"
JWT_SECRET="sua_chave_secreta_super_segura"
PORT=3000

```

4. Execute as migrações do Prisma para estruturar o banco de dados:

```bash
npx prisma generate
npx prisma db push

```

5. Inicie o servidor em modo de desenvolvimento:

```bash
npm run dev

```

A API estará disponível em `http://localhost:3000`.

---

## 🌐 Deploy da Aplicação

O ecossistema OrganizaTask está configurado para deploy contínuo utilizando as melhores práticas em infraestrutura serverless e edge:

* **Back-end:** Hospedado no [Render](https://render.com/).
* **Front-end:** Hospedado na Vercel. *(Repositório do front-end não incluso aqui).*

---

## 👨‍💻 Autor

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/leonard0antonio" title="Leonardo Antonio">
        <img src="https://avatars.githubusercontent.com/u/169267801?v=4" width="100px;" alt="Foto do leonardo no GitHub"/><br>
        <sub>
          <b>Leonardo Antonio</b>
        </sub>
      </a>
    </td>
  </tr>
</table>
