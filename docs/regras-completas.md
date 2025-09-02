# Regras Completas: Notebooks, Pontuação, XP e Tela de Escolha

**Projeto:** Formação Analista de Dados Interativa com GPT Humanizada
**Fase:** 0 – Passo 3 Atualizado
**Objetivo:** Documentar regras de nomenclatura, organização, pontuação, XP e fluxo de usuário pós-teoria, garantindo consistência e foco no usuário.

---

## 1️⃣ Nomenclatura e Organização dos Notebooks

```tree
/notebooks
    /mundoX_nome_do_mundo
        /topicoY_nome_do_topico
            /subtopicoZ_nome_do_subtopico
                teoria.ipynb
                quiz.ipynb
                desafio.ipynb
                exercicios.ipynb
```

**Descrição:**

* Mundo: nível do jogo (ex.: Fundamentos, Manipulação, Visualização)
* Tópico: subárea dentro do mundo (ex.: Python, NumPy)
* Subtópico: assunto específico (ex.: Funções, Listas)
* Tipos de notebooks: teoria, quiz, desafio, exercícios

### Padrões adicionais

* Scripts em `/src`: `faseX_moduloY_descricao.py`
* Classes: `CamelCase`
* Funções/variáveis: `snake_case`
* Commits Git: `[FaseX-PassoY] Descrição curta`

---

## 2️⃣ Regras de Pontuação e Notas

* **Nota final do subtópico:** 0-100
* Composição ponderada (não pesos iguais):

  * Quiz: peso variável (ex.: 40%)
  * Desafio: peso variável (ex.: 35%)
  * Exercícios: peso variável (ex.: 25%)
* Checkpoints na teoria não geram nota
* Exemplo de cálculo:

```txt
Quiz: 30/40, Desafio: 28/35, Exercicios: 20/25 → Nota Final: 78/100
```

---

## 3️⃣ Regras de XP

* Cada subtópico pode gerar **até 300 XP**

  * Quiz: até 100 XP
  * Desafio: até 100 XP
  * Exercícios: até 100 XP
* XP acumulado será exibido na tela de escolha
* Uso futuro do XP:

  * Desbloqueio de mundos/tópicos
  * Badges ou conquistas
  * Ranking interno
* Checkpoints na teoria não geram XP

---

## 4️⃣ Fluxo do Usuário e Tela de Escolha

Após concluir `teoria.ipynb`:

* Usuário vê **tela de escolha** com 3 botões:

  1. Quiz → abre `quiz.ipynb`
  2. Desafio → abre `desafio.ipynb`
  3. Exercícios → abre `exercicios.ipynb`
* Campo de **pontuação e XP acumulados** até o momento
* Feedback visual do progresso do usuário

### Layout Conceitual

```markdown
# Subtópico: Funções em Python

Parabéns! Você concluiu a teoria.

Pontuação atual: 78/100
XP acumulado: 245/300

[ Quiz ]    [ Desafio ]    [ Exercícios ]
```

* Cada botão abre o notebook correspondente
* Permite o usuário escolher ordem de avaliações
* Mostra progresso e incentiva engajamento gamificado

---

## 5️⃣ Observações

* Documento central de referência para todas as fases do projeto
* Flexível para adição de novos mundos, tópicos e subtópicos
* Mantém foco total no **usuário e experiência de aprendizado interativa**
