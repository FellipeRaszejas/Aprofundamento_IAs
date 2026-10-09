# 18 · Treinamento e inferência em escala

> **Status:** `[ ] Não iniciado` · `[ ] Em andamento` · `[ ] Em revisão` · `[ ] Validado`
>
> **Início:** ____/____/______ · **Conclusão:** ____/____/______ · **Horas estudadas:** ______
>
> **Autoavaliação (0 a 4):** ____ *(ver escala no README principal)*

## 🎯 Objetivo da etapa

Treinar e servir modelos grandes de forma eficiente e confiável.

## 📁 Estrutura sugerida da pasta

```
18-treinamento-e-inferencia-em-escala/
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

- [ ] Paralelismo de dados, tensor e pipeline
- [ ] FSDP, DeepSpeed, Megatron
- [ ] Mixed precision (FP16, BF16, FP8/FP4)
- [ ] Quantização: GGUF, AWQ, GPTQ
- [ ] Destilação e pruning
- [ ] Speculative decoding
- [ ] Continuous batching e PagedAttention
- [ ] KV-cache e gerenciamento de memória
- [ ] Servidores: vLLM, TGI, SGLang, Triton, Ollama
- [ ] Latência vs. vazão vs. custo
- [ ] Estabilidade de treino em larga escala e checkpoints
- [ ] Planejamento de capacidade

## ✅ Critérios de validação (capacidades)

Só marque se você consegue fazer **sem ajuda e sem copiar tutorial**. Ao marcar, anote a evidência (arquivo, link, relatório).

- [ ] Treino um modelo com paralelismo de dados em múltiplas GPUs  
  - Evidência: 
- [ ] Quantizo um modelo e meço perda de qualidade e ganho de velocidade  
  - Evidência: 
- [ ] Sirvo um modelo com vLLM ou equivalente e meço vazão e latência  
  - Evidência: 
- [ ] Explico continuous batching e PagedAttention  
  - Evidência: 
- [ ] Escolho a estratégia de paralelismo para um modelo e hardware dados  
  - Evidência: 
- [ ] Estimo memória necessária para treino e inferência  
  - Evidência: 

## 🛠️ Entregáveis obrigatórios

- [ ] Experimento de treino distribuído com relatório  
  - Link/caminho: 
- [ ] Benchmark de quantização (qualidade x velocidade)  
  - Link/caminho: 
- [ ] Serviço de inferência com testes de carga  
  - Link/caminho: 

## ❓ Perguntas de autoavaliação

Responda **de memória, em voz alta ou por escrito**, antes de consultar qualquer material. Depois confira e anote o que errou.

1. Quando usar paralelismo de tensor vs. de pipeline?
   - Resposta (sem consultar):

2. O que perde-se ao quantizar?
   - Resposta (sem consultar):

3. Por que o continuous batching aumenta a vazão?
   - Resposta (sem consultar):

4. Como estimar a memória de um LLM?
   - Resposta (sem consultar):

5. O que é speculative decoding?
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

