# 01 · Linguagem e texto (LLMs)

> **Status:** `[ ] Não iniciado` · `[ ] Em andamento` · `[ ] Em revisão` · `[ ] Validado`
>
> **Início:** ____/____/______ · **Conclusão:** ____/____/______ · **Horas estudadas:** ______
>
> **Autoavaliação (0 a 4):** ____ *(ver escala no README principal)*

## 🎯 Objetivo da etapa

Entender como LLMs são construídos, treinados, alinhados e usados, a ponto de implementar e adaptar um modelo.

## 📁 Estrutura sugerida da pasta

```
01-linguagem-e-texto-llms/
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

- [ ] Transformer: self-attention, multi-head, positional encoding (RoPE)
- [ ] Encoder, decoder e encoder-decoder
- [ ] Tokenização moderna (BPE, SentencePiece) e seus efeitos
- [ ] Scaling laws
- [ ] Pré-treino e pipeline de dados (filtragem, deduplicação, dados sintéticos)
- [ ] Fine-tuning supervisionado, LoRA e QLoRA
- [ ] Alinhamento: RLHF, DPO, GRPO, recompensas verificáveis
- [ ] Modelos de raciocínio e escala em tempo de teste
- [ ] Decodificação: greedy, sampling, temperatura, top-p
- [ ] KV-cache, GQA/MQA, FlashAttention, contexto longo
- [ ] Mixture of Experts e destilação
- [ ] Arquiteturas alternativas (State Space Models)
- [ ] Modelos abertos vs. fechados e licenças

## ✅ Critérios de validação (capacidades)

Só marque se você consegue fazer **sem ajuda e sem copiar tutorial**. Ao marcar, anote a evidência (arquivo, link, relatório).

- [ ] Implemento um mini-GPT do zero e o treino  
  - Evidência: 
- [ ] Explico atenção sem recorrer a analogias vagas  
  - Evidência: 
- [ ] Faço fine-tuning (LoRA) de um modelo aberto e meço o ganho  
  - Evidência: 
- [ ] Explico por que a tokenização gera comportamentos estranhos  
  - Evidência: 
- [ ] Escolho a estratégia de decodificação adequada para uma tarefa  
  - Evidência: 
- [ ] Explico a diferença entre SFT, RLHF e DPO  
  - Evidência: 

## 🛠️ Entregáveis obrigatórios

- [ ] Mini-GPT (estilo nanoGPT) com treino e amostragem  
  - Link/caminho: 
- [ ] Fine-tuning com avaliação antes/depois  
  - Link/caminho: 
- [ ] Relatório explicativo sobre scaling laws ou KV-cache com experimento  
  - Link/caminho: 

## ❓ Perguntas de autoavaliação

Responda **de memória, em voz alta ou por escrito**, antes de consultar qualquer material. Depois confira e anote o que errou.

1. Por que a atenção custa O(n²) e o que se faz a respeito?
   - Resposta (sem consultar):

2. O que RoPE resolve?
   - Resposta (sem consultar):

3. Quando fine-tuning é melhor que RAG?
   - Resposta (sem consultar):

4. O que o KV-cache guarda e por que acelera?
   - Resposta (sem consultar):

5. Qual a ideia central do DPO?
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

