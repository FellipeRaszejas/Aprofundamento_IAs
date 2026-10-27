# RAG e Engenharia de Contexto

O RAG e a engenharia de contexto trabalham juntos: um encontra a informação e o outro a organiza dentro do prompt.

## Sumário

1. [Diferença entre os dois](#1-diferença-entre-os-dois)
2. [Fluxo completo](#2-fluxo-completo)
3. [Vantagens do RAG](#3-vantagens-do-rag)

## 1. Diferença entre os dois

| | RAG | Engenharia de Contexto |
|---|---|---|
| **Papel** | Ferramenta que procura e recupera a informação correta na base de dados | Arte de organizar essa informação dentro do prompt final enviado ao LLM |

## 2. Fluxo completo

```
[Pergunta do Usuário]
       ↓
[Sistema RAG Procura e Encontra Documentos Relevantes]
       ↓
[Engenharia de Contexto Estrutura o Prompt: Instruções + Documentos + Pergunta]
       ↓
[LLM Gera Resposta Precisa e Baseada em Fatos]
```

## 3. Vantagens do RAG

| Vantagem | Descrição |
|---|---|
| **Respostas baseadas em fontes reais** | Minimiza drasticamente as alucinações |
| **Privacidade e segurança** | Não é necessário treinar ou fazer fine-tuning do modelo com dados confidenciais |
| **Atualização em tempo real** | Basta atualizar o banco de dados vetorial para que o sistema tenha informações novas imediatamente |