# Governança de IA

Este guia explica o que é governança de inteligência artificial, apresenta os quatro pilares arquiteturais da conformidade em IA, a classificação dos riscos e o ciclo de vida de um sistema de IA seguro.

## Sumário

1. [O que é Governança de IA](#1-o-que-é-governança-de-ia)
2. [Os Quatro Pilares Arquiteturais da Conformidade em IA](#2-os-quatro-pilares-arquiteturais-da-conformidade-em-ia)
3. [Transparência e Explicabilidade (XAI)](#3-transparência-e-explicabilidade-xai)
4. [Alinhamento e Comportamento (Safety & Alignment)](#4-alinhamento-e-comportamento-safety--alignment)
   - [Guardrails de entrada e de saída](#guardrails-de-entrada-e-de-saída)
5. [Gestão de Risco e Segurança de Dados (Security & Privacy)](#5-gestão-de-risco-e-segurança-de-dados-security--privacy)
6. [Auditoria e Rastreabilidade (Lineage & Audit Trails)](#6-auditoria-e-rastreabilidade-lineage--audit-trails)
7. [Classificação dos Riscos de IA](#7-classificação-dos-riscos-de-ia)
8. [O Ciclo de Vida](#8-o-ciclo-de-vida)
9. [Glossário Rápido](#9-glossário-rápido)

---

## 1. O que é Governança de IA

**Conceito:** governança de IA é o conjunto de **diretrizes**, **políticas**, **papéis organizacionais** e **controles de arquitetura** que transforma princípios éticos abstratos (como justiça, transparência e segurança) em **regras auditáveis**.

**No dia a dia:** é como o código de trânsito de uma cidade. A ideia abstrata de "trânsito seguro" vira regras concretas (semáforos, limites de velocidade, carteira de habilitação, radares) que qualquer pessoa pode conferir e cobrar.

**Por que a IA exige uma governança própria:** diferente dos softwares tradicionais, os sistemas de IA (especialmente os LLMs e os agentes) são **probabilísticos**, ou seja, podem gerar respostas diferentes para a mesma pergunta. Por isso, a governança não foca no código estático, e sim no **comportamento dinâmico** do modelo.

| Elemento da governança | O que representa |
|---|---|
| **Diretrizes** | Princípios e orientações gerais |
| **Políticas** | Regras formais da organização |
| **Papéis organizacionais** | Quem é responsável por quê |
| **Controle de arquitetura** | Mecanismos técnicos que aplicam as regras no sistema |

---

## 2. Os Quatro Pilares Arquiteturais da Conformidade em IA

| Pilar | Nome em inglês | Em uma frase |
|---|---|---|
| **1. Transparência e Explicabilidade** | XAI | Saber explicar por que o modelo respondeu o que respondeu |
| **2. Alinhamento e Comportamento** | Safety & Alignment | Impedir que o modelo produza conteúdo nocivo ou tendencioso |
| **3. Gestão de Risco e Segurança de Dados** | Security & Privacy | Proteger os dados durante todo o ciclo de vida da IA |
| **4. Auditoria e Rastreabilidade** | Lineage & Audit Trails | Poder refazer o caminho de cada resposta |

---

## 3. Transparência e Explicabilidade (XAI)

**Conceito:** os modelos de *deep learning* e os LLMs funcionam como **"caixas-pretas"**: são processos matemáticos complexos, executados em espaços vetoriais (arrays), que os humanos não conseguem auditar linha a linha. A **explicabilidade** (*Explainable AI*, XAI) é a capacidade de mapear **o porquê** de uma decisão ou resposta.

**No dia a dia:** é como um médico que, além de dar o diagnóstico, mostra os exames que o levaram àquela conclusão.

**Abordagem arquitetural:** em sistemas avançados, a explicabilidade é garantida por meio de:

| Técnica | O que faz |
|---|---|
| **Rastreabilidade de fonte (RAG auditável)** | Garante que toda resposta venha acompanhada da citação exata da base de dados utilizada |
| **Camadas de metadados** | Registram quais pesos de atenção ou prompts do sistema influenciaram a geração da saída |

---

## 4. Alinhamento e Comportamento (Safety & Alignment)

**Conceito:** é o mecanismo que impede que o modelo produza conteúdos nocivos, alucinações críticas, vazamento de segredos comerciais ou comportamentos tendenciosos (*bias*).

**No dia a dia:** é como o *guardrail* (a barreira de proteção) de uma estrada. Ele não dirige o carro, mas impede que um desvio vire um acidente.

### Guardrails de entrada e de saída

A segurança é aplicada com **guardrails** (barreiras de segurança), estruturas que ficam ao redor do LLM:

| Guardrail | Onde atua | O que faz |
|---|---|---|
| **Entrada** | Antes do LLM | Filtra o prompt do usuário para bloquear malwares, injeções de comando (*Prompt Injection*) e dados sensíveis (PII, informações pessoalmente identificáveis) |
| **Saída** | Depois do LLM | Filtra a resposta do modelo antes de chegar ao usuário, barrando conteúdo nocivo, vazamento de dados e alucinações críticas |

---

## 5. Gestão de Risco e Segurança de Dados (Security & Privacy)

**Conceito:** é a maneira como os dados circulam pelo ciclo de vida da IA, respeitando as leis de privacidade.

**No dia a dia:** é como a tarja preta em um documento oficial: o conteúdo continua útil, mas as informações pessoais ficam cobertas.

| Prática | O que faz | Exemplo |
|---|---|---|
| **Isolamento por contexto** | Impede que dados de uma empresa cruzem a "fronteira" para o modelo público das IAs | Dados internos nunca vão para uma IA pública |
| **Mascaramento de dados** | Ferramentas removem automaticamente CPF, nomes e senhas dos textos antes de irem para o banco vetorial ou para o LLM | O texto chega ao modelo sem os dados pessoais |

---

## 6. Auditoria e Rastreabilidade (Lineage & Audit Trails)

**Conceito:** é a garantia de que seja possível **rastrear os passos da IA**, por exemplo, caso ela esteja envolvida em um caso criminal que precise de investigação.

**No dia a dia:** é como a caixa-preta de um avião ou as câmeras de segurança de uma loja: ninguém espera usá-las, mas, se algo der errado, elas permitem reconstruir o que aconteceu.

**Abordagem arquitetural:** implementar **logs imutáveis** (que não podem ser alterados depois de gravados) para cada transação de inferência, isto é, para cada vez que o modelo recebe uma entrada e gera uma resposta.

---

## 7. Classificação dos Riscos de IA

**Conceito:** os sistemas de IA são classificados por nível de risco, e quanto maior o risco, maior o rigor da governança.

| Nível de risco | Descrição | Exemplo |
|---|---|---|
| **Inaceitável** | Contra a humanidade | Apoiar um suicídio |
| **Alto** | Exige cuidado com empresas e serviços, de RH até aviação | Sistemas usados em decisões de RH |
| **Limitado / mínimo** | Utilização comum do cotidiano | Uso comum no dia a dia |

---

## 8. O Ciclo de Vida

| 🛡️ Design Seguro (*By Design*) | → | 📡 Monitoramento em Tempo Real | → | 🔍 Auditoria Periódica |
|:---:|:---:|:---:|:---:|:---:|

| Etapa | O que fazer |
|---|---|
| **Design Seguro** | Definir regras rígidas de acesso e permissões antes de colocar o sistema em produção |
| **Monitoramento** | Acompanhar métricas de desvio de comportamento (*model drift*) e taxas de alucinação |
| **Auditoria** | Revisar logs e refinar as barreiras de segurança periodicamente |

---

## 9. Glossário Rápido

| Termo | Significado |
|---|---|
| **LLM** | *Large Language Model*, modelo de linguagem de grande porte |
| **XAI** | *Explainable AI*, IA explicável |
| **RAG** | *Retrieval-Augmented Generation*, o modelo consulta uma base de dados antes de responder |
| **PII** | *Personally Identifiable Information*, informações pessoalmente identificáveis |
| **Prompt Injection** | Ataque que insere comandos maliciosos no prompt para manipular o modelo |
| **Guardrail** | Barreira de segurança que filtra entradas e saídas do modelo |
| **Model drift** | Desvio do comportamento do modelo ao longo do tempo |
| **Alucinação** | Resposta falsa apresentada pelo modelo como se fosse verdadeira |