# Regras de Pontuação – Formação Analista de Dados Interativa com GPT Humanizada

## Objetivo

Definir como será calculada a nota do usuário em cada módulo/continente/planeta.

---

## Tipos de Atividades e Peso na Nota Final

| Atividade          | Peso (%) |
|-------------------|----------|
| Quiz               | 30       |
| Exercícios         | 40       |
| Desafios           | 30       |

**Observações:**

- A nota final de cada continente será a soma ponderada das atividades.
- O usuário poderá refazer quizzes até 3x, mantendo a maior nota.
- Desafios só podem ser feitos 1x, com limite de tempo definido.
- Exercícios têm 1 tentativa, focados em avaliação de fixação prática.

---

## Tentativas e Limites

- **Quiz:** 3 tentativas → maior pontuação considerada.
- **Exercício:** 1 tentativa → entrega única.
- **Desafio:** 1 tentativa → tempo máximo definido, entrega obrigatória.

---

## Cálculo de Nota

`NOTA_FINAL = (QUIZ x 0.3) + (EXERCICIOS x 0.4) + (DESAFIO x 0.3)`

---

## Validação

- Cada atividade terá feedback imediato indicando acertos/parciais/erros.
- A nota será atualizada dinamicamente no dashboard do usuário.
- Usuário só desbloqueia próximo continente/planeta ao atingir nota mínima definida (ex.: 70/100).
