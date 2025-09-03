# Fase 01 – Fluxo de Navegação e Interações do Usuário

## 1. Onboarding

- Objetivo: Introduzir o usuário à plataforma e à "Formação Analista de Dados
  Interativa".
- Componentes:
  - Mensagem de boas-vindas / vídeo introdutório
  - Botão: "Começar Jornada"
- Transições:
  - Ao clicar em "Começar Jornada" → Tela de Dashboard

## 2. Dashboard

- Objetivo: Central de acesso aos mundos (galáxias), progresso, badges e XP
- Componentes:
  - Lista de Galáxias (Mundos)
  - Barras de progresso por galáxia
  - Notificação de badges conquistadas
  - Botão "Perfil" → Tela Perfil
- Transições:
  - Clicar em uma galáxia → Tela do Mundo selecionado
  - Clicar em "Perfil" → Tela Perfil

## 3. Tela do Mundo (Galáxia)

- Objetivo: Apresentar os módulos (planetas) de cada galáxia
- Componentes:
  - Lista de Planetas (Módulos)
  - Barras de progresso do planeta
  - Indicação de planetas desbloqueados/bloqueados
- Transições:
  - Clicar em um planeta desbloqueado → Tela do Módulo (continente)

## 4. Tela do Módulo (Planeta)

- Objetivo: Apresentar os tópicos (continentes) do módulo
- Componentes:
  - Lista de Continentes (tópicos)
  - Status: Completo / Em andamento / Bloqueado
  - Botão "Voltar para Mundo"
- Transições:
  - Clicar em um continente → Tela de Teoria do tópico

## 5. Tela de Teoria (Continente)

- Objetivo: Exibir conteúdo do tópico com exemplos práticos e checkpoints
- Componentes:
  - Seção Teoria (textos, exemplos, código)
  - Checkpoints integrados (mini quizzes ou questões rápidas)
  - Botão "Concluir Teoria"
- Transições:
  - Ao concluir teoria → Tela de Avaliações (quiz, exercício, desafio)

## 6. Tela de Avaliações

- Objetivo: Testar conhecimento do usuário em múltiplas atividades
- Componentes:
  - Botão Quiz (10 questões, 3 tentativas, XP proporcional)
  - Botão Exercícios (6–10 questões dissertativas)
  - Botão Desafio (criar código, 1 tentativa, tempo definido)
  - Campo exibindo nota e XP atual
- Transições:
  - Ao concluir qualquer avaliação → Atualiza XP e badges → Permite continuar
    para próximo tópico

## 7. Tela de Resultados e Feedback

- Objetivo: Exibir desempenho do usuário e recompensas
- Componentes:
  - Nota obtida no quiz/exercício/desafio
  - XP ganho
  - Badges conquistadas
  - Botão "Voltar para Módulo" ou "Próximo Tópico"
- Transições:
  - Clicar "Voltar para Módulo" → Tela do Módulo
  - Clicar "Próximo Tópico" → Tela de Teoria do próximo continente

## 8. Tela Perfil

- Objetivo: Exibir conquistas, badges, XP total e progresso geral
- Componentes:
  - Estatísticas de XP e badges
  - Lista de mundos e módulos concluídos
  - Botão "Voltar para Dashboard"
- Transições:
  - Clicar "Voltar para Dashboard" → Dashboard
