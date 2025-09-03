# Documentação Estratégica Final – FullStack com GPT Humanizado

## 1️⃣ Visão Geral do Projeto

**Objetivo:**  
Plataforma gamificada de ensino de análise de dados com narrativa interativa e
progressão adaptativa, usando:

- **Frontend:** React SPA
- **Backend:** Python (FastAPI ou Flask)
- **Gamificação:** XP, badges, checkpoints
- **Persistência:** user_progress.json
- **Estrutura modular:** Galáxias → Planetas → Continentes → Satélites

**Pilares do projeto:**

1. Ensino gamificado e interativo
2. Modularidade e escalabilidade
3. Feedback instantâneo e progressão adaptativa
4. Facilidade de expansão futura

---

## 2️⃣ Hierarquia de Conteúdo

```tree
Galáxia (macrofase do aprendizado)
 └── Planeta (módulo temático)
      └── Continente (submódulos/aulas)
           └── Satélite (opcional: conteúdos extras/bônus)
```

**Exemplo aplicado a Galáxia Python:**

- **Galáxia:** Python Fundamentals
  - **Planeta:** Python Básico
    - **Continente:** Tipos de Dados
      - **Satélite:** Exercícios Avançados de Tipos
    - **Continente:** Loops e Condicionais
  - **Planeta:** NumPy
    - **Continente:** Arrays e Operações Básicas
      - **Satélite:** Operações Avançadas / Broadcasting
    - **Continente:** Funções Matemáticas e Estatísticas

---

## 3️⃣ Gamificação e Regras de Progressão

**Componentes de gamificação:**

- **XP:** ganho ao completar continentes, planetas ou satélites
- **Badges:** conquistadas ao cumprir pré-requisitos ou desafios especiais
- **Checkpoints:** salvamento automático do progresso

**Desbloqueio hierárquico:**

- Completar todos os continentes de um planeta → desbloqueia próximo planeta
- Completar todos os planetas de uma galáxia → desbloqueia próxima galáxia
- Satélites acessíveis apenas após concluir o continente correspondente

**Fluxo de progresso:**

1. Usuário completa continente → XP + badges + checkpoint
2. Satélite (se houver) → XP bônus + badges especiais
3. Planeta concluído → desbloqueia próximo planeta
4. Galáxia concluída → desbloqueia próxima galáxia

---

## 4️⃣ Estrutura Conceitual do Backend

**Arquitetura (backend/):**

```tree
app/
├── main.py          # Entry point FastAPI
├── models.py        # Modelos de dados (User, Progresso, Módulos)
├── schemas.py       # Pydantic schemas requests/responses
├── database.py      # Manipulação de user_progress.json
├── routes/
│   ├── auth.py      # Login/cadastro
│   ├── progress.py  # Progresso do usuário
│   └── modules.py   # Módulos (continentes, satélites)
├── services/        # XP, badges, desbloqueio
└── utils.py         # Funções utilitárias
```

**Endpoints conceituais:**

| Endpoint                | Método | Função                                                                          |
| ----------------------- | ------ | ------------------------------------------------------------------------------- |
| `/auth/login`           | POST   | Autenticação do usuário                                                         |
| `/auth/register`        | POST   | Cadastro de novo usuário                                                        |
| `/progress`             | GET    | Retorna progresso (galáxia → planeta → continente → satélite)                   |
| `/progress`             | POST   | Atualiza progresso após completar continente/satélite                           |
| `/modules/:id/complete` | POST   | Marca módulo como concluído, atualiza XP/badges, desbloqueia próximos elementos |

**Serviços Backend:**

- **XP Service:** calcula XP por continente, satélite, planeta
- **Badge Service:** atribui badges quando critérios são cumpridos
- **Unlock Service:** desbloqueia planetas e galáxias automaticamente

**Exemplo de JSON de progresso do usuário:**

```json
{
  "user_id": "12345",
  "current_galaxy": "Python Fundamentals",
  "planets": [
    {
      "planet_id": "python_basico",
      "continents": [
        {
          "continent_id": "tipos_dados",
          "completed": true,
          "xp_earned": 20,
          "badges": ["Iniciante Tipos"]
        },
        {
          "continent_id": "loops_condicionais",
          "completed": false,
          "xp_earned": 0,
          "badges": []
        }
      ],
      "satellites": [
        {
          "satellite_id": "exercicios_avancados_tipos",
          "completed": false,
          "xp_earned": 0,
          "badges": []
        }
      ]
    }
  ]
}
```

---

## 5️⃣ Estrutura Conceitual do Frontend

**Componentes React:**

- `GalaxyPage.js` → exibe planetas desbloqueados
- `PlanetPage.js` → exibe continentes do planeta
- `ContinentPage.js` → exibe módulos do continente
- `SatellitePage.js` → exibe conteúdos extras/bônus (opcional)
- `ProgressBar.js` → mostra XP e progresso geral
- `Badge.js` → exibe badges conquistadas

**Serviços de comunicação com backend (services/api.js):**

```javascript
login(credentials)
getProgress(userId)
updateProgress(data)
completeModule(moduleId, userId)
```

**Fluxo do jogador (Frontend):**

1. Login → backend retorna progresso completo
2. Carregar galáxia atual, planetas desbloqueados
3. Selecionar planeta → exibir continentes
4. Completar continentes → atualizar progresso e XP
5. Satélites (opcional) → XP bônus e badges especiais
6. Desbloqueio sequencial de planetas e galáxias

---

## 6️⃣ Protocolos de Teste Conceituais

**Backend:**

- Testar endpoints de autenticação, progresso, módulos
- Simular fluxo completo do jogador
- Validar XP, badges e desbloqueios

**Frontend:**

- Testar renderização de galáxias, planetas, continentes e satélites
- Testar chamadas API e atualização de progresso
- Validar componentes de quizzes, feedback e progress bar

---

## 7️⃣ Expansão Futura

- Adicionar novas galáxias → JSON de configuração modular
- Satélites para conteúdos extras ou bônus
- Integração de APIs externas (Web Scraping, ML simples)
- Leaderboard e tracking competitivo
- Certificações internas ou badges digitais exportáveis

---

## 8️⃣ Checklist Final da Documentação

✅ Estrutura hierárquica atualizada (Galáxias → Planetas → Continentes →
Satélites)  
✅ Estrutura conceitual do backend e endpoints  
✅ Estrutura conceitual do frontend e componentes  
✅ Regras de gamificação e progressão  
✅ JSON de progresso atualizado com hierarquia correta  
✅ Protocolos de teste conceituais  
✅ Estratégia de expansão futura
