# 02 · Context Engineering, prompts e RAG

> **Status:** `[ ] Não iniciado` · `[ ] Em andamento` · `[ ] Em revisão` · `[ ] Validado`
>
> **Início:** ____/____/______ · **Conclusão:** ____/____/______ · **Horas estudadas:** ______
>
> **Autoavaliação (0 a 4):** ____ *(ver escala no README principal)*

## 🎯 Objetivo da etapa

Dar ao modelo o contexto certo e medir se funciona, com avaliação sistemática em vez de tentativa e erro.

## 📁 Estrutura sugerida da pasta

```
02-context-engineering-e-rag/
├── README.md          ← este arquivo (validação)
├── notas/             ← resumos com suas próprias palavras
├── exercicios/        ← implementações do zero, listas, katas
├── projetos/          ← entregáveis desta etapa
├── experimentos/      ← logs, configurações, métricas, resultados reproduzíveis
├── referencias/       ← papers, links, anotações de livros e cursos
└── evidencias/        ← prints, relatórios, links de repositório/demo, gravações
```

## 📚 Checklist de tópicos

Marque quando você **estudou e consegue explicar** o tópico, não apenas leu. Itens com nomes de ferramentas e modelos mudam rápido: **confirme o que está vigente** antes de estudar.

- [ ] Anatomia do contexto: instruções, exemplos, documentos, memória, ferramentas
- [ ] Técnicas: zero/few-shot, CoT, ReAct, auto-consistência
- [ ] Structured outputs e geração restrita
- [ ] RAG: chunking, embeddings, indexação
- [ ] Busca híbrida (densa + BM25) e re-ranking
- [ ] GraphRAG, RAG modular e agêntico
- [ ] Cache de prompt e compressão de contexto
- [ ] Memória de curto e longo prazo
- [ ] Prompt injection e segurança do contexto
- [ ] Versionamento de prompts
- [ ] Avaliação de RAG: fidelidade, relevância, recall de contexto
- [ ] DSPy e otimização programática de prompts

## ✅ Critérios de validação (capacidades)

Só marque se você consegue fazer **sem ajuda e sem copiar tutorial**. Ao marcar, anote a evidência (arquivo, link, relatório).

- [ ] Construo um conjunto de avaliação antes de otimizar prompts  
  - Evidência: 
- [ ] Projeto um pipeline de RAG e identifico onde ele falha  
  - Evidência: 
- [ ] Comparo estratégias de chunking com métricas  
  - Evidência: 
- [ ] Implemento re-ranking e meço o efeito  
  - Evidência: 
- [ ] Defendo um sistema contra prompt injection básica  
  - Evidência: 
- [ ] Decido quando RAG, fine-tuning ou contexto longo é melhor  
  - Evidência: 

## 🛠️ Entregáveis obrigatórios

- [ ] Sistema RAG completo com avaliação (golden set)  
  - Link/caminho: 
- [ ] Relatório comparando chunking, busca híbrida e re-ranking  
  - Link/caminho: 
- [ ] Biblioteca versionada de prompts com testes  
  - Link/caminho: 

## ❓ Perguntas de autoavaliação

Responda **de memória, em voz alta ou por escrito**, antes de consultar qualquer material. Depois confira e anote o que errou.

1. Por que a qualidade da recuperação limita a resposta?
   - Resposta (sem consultar):

2. O que é busca híbrida e quando ajuda?
   - Resposta (sem consultar):

3. Como medir fidelidade (faithfulness)?
   - Resposta (sem consultar):

4. O que é injeção de prompt indireta?
   - Resposta (sem consultar):

5. Quando contexto longo substitui RAG?
   - Resposta (sem consultar):

## 🔎 Lacunas e dúvidas abertas

| Data | Dúvida / lacuna | Plano para resolver | Resolvido? |
|---|---|---|---|
|  |  |  | [ ] |

## 🧾 Materiais consultados

| Tipo (livro, curso, paper, vídeo) | Título / link | Partes consultadas | Nota (0-5) |
|---|---|---|---|
|  |  |  |  |

## 🏁 Parecer final da etapa

Esta etapa está **validada** quando:

- [ ] Todos os critérios de validação estão marcados com evidência.
- [ ] Todos os entregáveis obrigatórios estão concluídos e **reproduzíveis** (código, dados e instruções permitem refazer).
- [ ] Os resultados foram **avaliados com método** (métricas, baseline e análise de erros), não só observados.
- [ ] Você acertou ao menos 80% das perguntas de autoavaliação sem consultar.
- [ ] Você conseguiu explicar a etapa para outra pessoa (ou gravou uma explicação) sem apoio de anotações.
- [ ] Alguém revisou pelo menos um dos seus entregáveis e você incorporou o feedback.
- [ ] Você registrou as lacunas restantes e decidiu quando voltar a elas.

**Data da validação:** ____/____/______

**Observações finais:**

