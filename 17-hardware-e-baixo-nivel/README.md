# 17 · Hardware e programação de baixo nível

> **Status:** `[ ] Não iniciado` · `[ ] Em andamento` · `[ ] Em revisão` · `[ ] Validado`
>
> **Início:** ____/____/______ · **Conclusão:** ____/____/______ · **Horas estudadas:** ______
>
> **Autoavaliação (0 a 4):** ____ *(ver escala no README principal)*

## 🎯 Objetivo da etapa

Entender o hardware e o software de baixo nível que determinam desempenho e custo em IA.

## 📁 Estrutura sugerida da pasta

```
17-hardware-e-baixo-nivel/
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

- [ ] Arquitetura de computadores e hierarquia de memória
- [ ] GPUs: SMs, warps, memória global/compartilhada
- [ ] TPUs, NPUs e aceleradores
- [ ] CUDA e noções de kernels
- [ ] Triton (linguagem de kernels)
- [ ] Compiladores de ML: torch.compile, XLA, MLIR
- [ ] FlashAttention por dentro
- [ ] Intensidade aritmética e modelo roofline
- [ ] Interconexões: NVLink, InfiniBand
- [ ] HBM e gargalos de memória
- [ ] Profiling de GPU
- [ ] Eficiência energética e custo

## ✅ Critérios de validação (capacidades)

Só marque se você consegue fazer **sem ajuda e sem copiar tutorial**. Ao marcar, anote a evidência (arquivo, link, relatório).

- [ ] Escrevo um kernel simples e comparo com a implementação padrão  
  - Evidência: 
- [ ] Faço profiling e identifico se um modelo é limitado por memória ou por computação  
  - Evidência: 
- [ ] Explico por que a FlashAttention é mais rápida  
  - Evidência: 
- [ ] Uso o modelo roofline para raciocinar sobre desempenho  
  - Evidência: 
- [ ] Explico a diferença entre GPU e TPU  
  - Evidência: 
- [ ] Estimo o custo de treinar ou servir um modelo  
  - Evidência: 

## 🛠️ Entregáveis obrigatórios

- [ ] Kernel (CUDA ou Triton) com benchmark  
  - Link/caminho: 
- [ ] Relatório de profiling de um modelo  
  - Link/caminho: 
- [ ] Estimativa de custo e capacidade documentada  
  - Link/caminho: 

## ❓ Perguntas de autoavaliação

Responda **de memória, em voz alta ou por escrito**, antes de consultar qualquer material. Depois confira e anote o que errou.

1. Por que muitos modelos são limitados por memória?
   - Resposta (sem consultar):

2. O que é o modelo roofline?
   - Resposta (sem consultar):

3. Como a FlashAttention reduz acessos à memória?
   - Resposta (sem consultar):

4. O que um compilador de ML otimiza?
   - Resposta (sem consultar):

5. Qual a função das interconexões no treino distribuído?
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

