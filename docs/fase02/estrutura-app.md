# Fase 2 – Backend / Infraestrutura | Documento de Implementação

**Objetivo:** Criar a base de dados, APIs, autenticação, lógica de armazenamento
de progresso, conteúdo e integração com frontend interativo.

---

## 1. Tecnologias Escolhidas

| Componente       | Tecnologia            | Justificativa                                                                                 |
| ---------------- | --------------------- | --------------------------------------------------------------------------------------------- |
| Backend          | Python + FastAPI      | Performance, fácil integração com Python, async, documentação automática (Swagger)            |
| Banco de Dados   | PostgreSQL            | Confiável, relacional, escalável, fácil modelagem para usuários, galáxias, planetas e quizzes |
| Autenticação     | JWT (JSON Web Tokens) | Segurança, stateless, integração simples com SPA                                              |
| Containerização  | Docker                | Facilita deploy, consistência entre dev e produção                                            |
| Frontend inicial | React SPA             | Interatividade, componentização, integração com gamificação e dashboards                      |

---

## 2. Estrutura do Backend

---

/backend │ ├─ app/ │ ├─ main.py # Inicialização do FastAPI │ ├─ config.py #
Configurações (DB, JWT, variáveis de ambiente) │ ├─ models.py # Modelos
SQLAlchemy (User, Galaxia, Planeta, Continente, Quiz, Desafio, XP, Badges) │ ├─
schemas.py # Pydantic schemas para request/response │ ├─ crud.py # Funções CRUD
para cada entidade │ ├─ auth.py # Rotas e lógica de autenticação JWT │ ├─ api/ │
│ ├─ users.py │ │ ├─ galaxias.py │ │ ├─ planetas.py │ │ ├─ continentes.py │ │ ├─
quizzes.py │ │ └─ desafios.py │ └─ utils.py # Funções auxiliares, validações,
calculo de XP │ ├─ tests/ # Testes unitários e integração ├─ Dockerfile ├─
docker-compose.yml ├─ requirements.txt └─ README.md

---

## 3. Banco de Dados – Modelagem

### 3.1 Entidades Principais

1. **User**

   - id (PK)
   - nome
   - email (único)
   - senha_hash
   - data_criacao
   - XP_total
   - badges (JSON ou relação N:N)

2. **Galaxia**

   - id (PK)
   - nome
   - descricao
   - ordem
   - status (desbloqueado/travado)

3. **Planeta**

   - id (PK)
   - galaxia_id (FK)
   - nome
   - descricao
   - ordem

4. **Continente**

   - id (PK)
   - planeta_id (FK)
   - nome
   - descricao
   - ordem

5. **Quiz**

   - id (PK)
   - continente_id (FK)
   - perguntas (JSON: pergunta, alternativas, correta)
   - peso_total
   - xp_total

6. **Desafio**

   - id (PK)
   - continente_id (FK)
   - descricao
   - requisitos
   - xp

7. **Exercício**

   - id (PK)
   - continente_id (FK)
   - perguntas (JSON)
   - xp

8. **Progresso**
   - id (PK)
   - user_id (FK)
   - continente_id (FK)
   - quiz_score
   - exercicio_score
   - desafio_score
   - XP_atual

---

## 4. Autenticação JWT

- Endpoint `/api/login` → Recebe email e senha, retorna token JWT
- Endpoint `/api/register` → Cria usuário e retorna token JWT
- Middleware valida JWT em todas rotas protegidas
- Tokens armazenados no frontend via **localStorage** ou **cookies HttpOnly**

---

## 5. Endpoints Planejados

| Método | Endpoint                     | Descrição                                                                   |
| ------ | ---------------------------- | --------------------------------------------------------------------------- |
| POST   | /api/register                | Criar novo usuário                                                          |
| POST   | /api/login                   | Autenticar usuário e gerar token JWT                                        |
| GET    | /api/user/progresso          | Retornar progresso do usuário (XP, badges, galáxias, planetas, continentes) |
| GET    | /api/galaxias                | Listar todas as galáxias                                                    |
| GET    | /api/planetas/{id}           | Detalhes do planeta, continentes e conteúdo                                 |
| GET    | /api/continentes/{id}        | Detalhes do continente (teoria, checkpoints, exercícios, quizzes)           |
| POST   | /api/quiz/{id}/resposta      | Registrar respostas do quiz e calcular XP                                   |
| POST   | /api/desafio/{id}/resposta   | Registrar submissão de desafio e XP                                         |
| POST   | /api/exercicio/{id}/resposta | Registrar respostas do exercício e XP                                       |
| GET    | /api/leaderboard             | Ranking dos usuários (opcional)                                             |

---

## 6. Gamificação – XP e Badges

- **XP**

  - Teoria: checkpoints → XP inicial (ex: 50 XP)
  - Quiz: máximo 100 XP
  - Exercícios: máximo 100 XP
  - Desafio: máximo 100 XP
  - **Total por continente:** 300 XP

- **Badges**
  - Conquista por continente concluído
  - Conquista especial por milestones (ex: completar 3 galáxias)

> Observação: Uso do XP no frontend para desbloqueios, progressão e feedback
> visual.

---

## 7. Docker e Deploy

- **Dockerfile:** criar imagem com FastAPI + Uvicorn
- **docker-compose.yml:** container backend + PostgreSQL + volumes persistentes
- Permite testes locais consistentes e futura implantação em cloud (AWS, GCP,
  Heroku)

---

## 8. Boas Práticas e Checklist de Implementação

- [ ] Criar estrutura de diretórios conforme especificado
- [ ] Configurar banco de dados PostgreSQL e rodar migrations iniciais
- [ ] Implementar autenticação JWT e middleware de proteção
- [ ] Criar endpoints CRUD para galáxias, planetas, continentes, quizzes,
      exercícios e desafios
- [ ] Implementar cálculo de XP e badges
- [ ] Testes unitários para endpoints principais
- [ ] Integrar com frontend React SPA via fetch/axios
- [ ] Dockerizar backend e banco de dados
- [ ] Documentar endpoints (Swagger)
- [ ] Revisão e validação interna antes de Fase 3

---

## 9. Observações do Diretor

- Prioridade inicial: Galáxia 1 → Planeta 1 → Continente 1 (Fundamentos de
  Dados)
- Backend deve ser modular para adicionar galáxias, planetas e continentes
  futuros facilmente
- Garantir consistência de XP e badges entre backend e frontend
- Todos endpoints e lógicas de gamificação devem ser documentados antes de
  iniciar implementação
