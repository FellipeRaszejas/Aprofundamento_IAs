# Estratégias para Guiar Modelos de IA

Este guia reúne estratégias para escrever prompts que obtêm respostas precisas de modelos de linguagem, a partir da analogia de uma criança prodígio. Ele complementa a estrutura básica de prompts, descrita em [`../prompts/README.md`](../prompts/README.md).

## Sumário

1. [A analogia: a IA como criança prodígio](#1-a-analogia-a-ia-como-criança-prodígio)
2. [Instruções claras e diretas](#2-instruções-claras-e-diretas)
3. [Formato e estrutura da saída](#3-formato-e-estrutura-da-saída)
4. [Cadeia de pensamento (Chain-of-Thought)](#4-cadeia-de-pensamento-chain-of-thought)
5. [Reforço das regras no final](#5-reforço-das-regras-no-final)
6. [Decomposição de tarefas (Prompt Chaining)](#6-decomposição-de-tarefas-prompt-chaining)
7. [Guardrails: limites e restrições](#7-guardrails-limites-e-restrições)
8. [Sintaxe limpa e delimitadores](#8-sintaxe-limpa-e-delimitadores)
9. [Resumo](#9-resumo)

## 1. A analogia: a IA como criança prodígio

![Criança sentada em frente a dois computadores, com balões de pensamento que mostram pintura, ciência, música, robôs e código](imagens/analogia-ia-crianca-prodigio.jpg)

*Uma criança com muito conhecimento em várias áreas. Assim como ela, a IA sabe muito, mas precisa ser orientada com clareza.*

A analogia usada aqui é a de uma criança de cinco anos que tem acesso a todo o conhecimento existente. Ela sabe muitas coisas, mas não entende intenções implícitas como um adulto faria.

A IA tem capacidade técnica grande para executar tarefas complexas. No entanto, sem direção explícita, ela interpreta o pedido de forma literal ou superficial, e o resultado pode ser vago ou fora do objetivo. As estratégias a seguir servem para dar essa direção.

## 2. Instruções claras e diretas

Defina exatamente o que deve ser feito, sem rodeios e sem ambiguidades.

```text
Fale sobre vendas.
```

Esse pedido é vago. A IA não sabe se você quer um resumo, uma explicação para iniciantes, uma lista de técnicas ou uma análise de dados.

```text
Explique o que é uma meta de vendas mensal, em até 3 parágrafos, para um estagiário de comércio.
```

Esse pedido define a tarefa (explicar), o escopo (meta mensal), o tamanho (até 3 parágrafos) e o público (estagiário).

## 3. Formato e estrutura da saída

Especifique o formato esperado (JSON, Markdown, tabela, lista) e o esquema exato dos campos ou seções. Assim, a resposta sai organizada e pode ser usada por outro programa, se for o caso.

```text
Liste os produtos em JSON, no formato:
[{"nome": "...", "preco": 0.00, "estoque": 0}]
```

Quando o formato não é definido, a mesma informação pode vir como parágrafo, lista ou tabela, o que dificulta o uso posterior.

## 4. Cadeia de pensamento (Chain-of-Thought)

A **Chain-of-Thought (CoT)** é uma técnica em que o modelo expõe o raciocínio passo a passo antes de dar a conclusão. Em tarefas analíticas, isso reduz erros, e o processo fica mais fácil de revisar e estudar.

```text
Calcule o total do pedido: 3 camisetas a R$ 49,90 e 1 calça a R$ 120,00,
com desconto de 10% sobre o total. Mostre cada passo antes do resultado final.
```

| Quando usar CoT | Quando não é necessário |
|---|---|
| Cálculos, lógica e análise de dados | Perguntas factuais simples |
| Decisões com vários critérios | Reescrita ou tradução de texto |
| Revisão de código ou de processo | Respostas curtas, como uma palavra |

## 5. Reforço das regras no final

Modelos tendem a dar mais atenção ao início e ao fim da janela de contexto. Em textos longos, uma regra escrita no meio pode ser ignorada. Por isso, repita as restrições essenciais no final do prompt.

```text
[...contexto longo e dados extensos...]

Lembrete final: responda somente em JSON e não invente informações.
```

Essa repetição é útil em prompts longos. Em prompts curtos, ela costuma ser desnecessária.

## 6. Decomposição de tarefas (Prompt Chaining)

Prompts com muitos requisitos ao mesmo tempo aumentam a perda de foco e reduzem a qualidade. Divida o problema em etapas menores e sequenciais, em que a saída de uma etapa vira a entrada da próxima.

```text
Etapa 1: Extraia os nomes dos clientes da lista abaixo, em uma lista simples.
Etapa 2: Com a lista da etapa 1, conte quantos clientes compraram mais de uma vez.
Etapa 3: Com o total da etapa 2, escreva um resumo de uma frase para a diretoria.
```

Cada etapa tem uma tarefa só, o que facilita conferir o resultado antes de avançar.

## 7. Guardrails: limites e restrições

Guardrails são fronteiras explícitas sobre o que o modelo pode ou não fazer. Eles restringem o escopo e reduzem alucinações e desvios do tema.

```text
Você responde somente perguntas sobre o manual do produto anexado.
Se a resposta não estiver no manual, diga "Não encontrei essa informação no manual".
Não faça recomendações de outros produtos.
```

A regra de fallback (o que fazer quando a informação não existe) é tão importante quanto a regra principal, porque evita respostas inventadas.

## 8. Sintaxe limpa e delimitadores

Organize o prompt com pontuação precisa e separadores estruturais, como aspas triplas (`"""`), tags XML ou cabeçalhos Markdown. Eles isolam instruções, exemplos e dados de entrada, para que o modelo não confunda um com o outro.

Esse tema foi detalhado na seção 6 de [`../prompts/README.md`](../prompts/README.md), com exemplos.

## 9. Resumo

| Estratégia | Problema que resolve | Exemplo de uso |
|---|---|---|
| Instruções claras | Pedido vago e interpretação literal | Definir tarefa, escopo e tamanho |
| Formato de saída | Resposta desorganizada | Pedir JSON com campos fixos |
| Chain-of-Thought | Erros em tarefas analíticas | "Mostre cada passo antes do resultado" |
| Reforço no final | Regras ignoradas em textos longos | Repetir restrições ao fim do prompt |
| Prompt chaining | Perda de foco em tarefas complexas | Dividir em etapas sequenciais |
| Guardrails | Alucinação e desvio de tema | Limitar o escopo e definir fallback |
| Delimitadores | Dados confundidos com instruções | Usar `"""` ou tags XML |