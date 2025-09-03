# Documentação de Telas – Fase 01: Design UX/UI

## Formação Analista de Dados Interativa com GPT Humanizada

---

## 1. Tela de Onboarding

**Objetivo:** Apresentar a
 plataforma e guiar o usuário no início da experiência.  
**Elementos:**  

- Boas-vindas com breve descrição da jornada.  
- Botão "Iniciar" para criar conta ou logar.  
- Possibilidade futura de vídeo explicativo (IA).  
**Interações:**  
- Ao clicar em "Iniciar", direciona para cadastro/login.  
- Exibe resumo de badges e XP caso o usuário já tenha histórico.  

---

## 2. Tela de Dashboard Principal

**Objetivo:** Mostrar status geral do usuário e progresso na jornada.  
**Elementos:**  

- Painel de progresso geral (Galáxias/Planetas/Continentes).  
- Indicador de XP total e badges adquiridos.  
- Botões para acessar o próximo planeta ou continentes desbloqueados.  
- Notificações de desafios ou módulos concluídos.  
**Interações:**  
- Clique em galáxia/planeta leva ao módulo correspondente.  
- Atualização dinâmica de XP e badges.  

---

## 3. Tela de Módulo (Planeta)

**Objetivo:** Apresentar o conteúdo de cada módulo/planeta.  
**Elementos:**  

- Lista de continentes (tópicos) com status (não iniciado, em progresso, concluído).  
- Barra de progresso do módulo.  
- Botão "Iniciar Continente" para começar a estudar.  
**Interações:**  
- Ao iniciar um continente, abre tela de teoria.  
- Ao finalizar, habilita quiz, exercícios e desafios.  

---

## 4. Tela de Teoria (Continente)

**Objetivo:** Entregar conteúdo didático, exemplos e checkpoints.  
**Elementos:**  

- Texto explicativo com exemplos práticos.  
- Blocos de código interativo (Python, visualizações).  
- Questões de checkpoint no meio do conteúdo.  
- Barra de progresso do continente.  
**Interações:**  
- Usuário responde checkpoints → feedback imediato.  
- Ao finalizar teoria, botão "Ir para Avaliações" é habilitado.  

---

## 5. Tela de Avaliações

**Objetivo:** Testar conhecimento adquirido em teoria.  
**Elementos:**  

- Três botões: Quiz, Exercícios, Desafios.  
- Indicador de nota atualizada dinamicamente.  
- Tempo restante para desafios, se aplicável.  
**Interações:**  
- Quiz: 10 questões múltipla escolha, 3 tentativas máximas.  
- Exercícios: 6–10 questões dissertativas, 1 tentativa.  
- Desafios: 1 tentativa, tempo definido.  
- Ao finalizar cada atividade, XP e nota atualizam automaticamente.  

---

## 6. Tela de Resultados e Feedback

**Objetivo:** Mostrar desempenho e desbloquear próximos módulos.  
**Elementos:**  

- Nota final do continente.  
- XP ganho.  
- Badges adquiridos.  
- Botão "Continuar para próximo continente/planeta".  
**Interações:**  
- Atualiza dashboard com progresso total.  
- Bloqueia próximo módulo se nota mínima não atingida.  

---

## 7. Tela de Perfil do Usuário

**Objetivo:** Visualizar histórico, conquistas e progresso.  

**Elementos:**  

- Lista de badges e XP acumulado.  
- Galáxias, planetas e continentes completados.  
- Estatísticas de quizzes, exercícios e desafios.  
**Interações:**  
- Permite consultar desempenho de cada módulo.  
- Possibilidade futura de ajustes de perfil e preferências.
