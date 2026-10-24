# 05 · Geração de imagem

> **Status:** `[ ] Não iniciado` · `[ ] Em andamento` · `[ ] Em revisão` · `[ ] Validado`
>
> **Início:** ____/____/______ · **Conclusão:** ____/____/______ · **Horas estudadas:** ______
>
> **Autoavaliação (0 a 4):** ____ *(ver escala no README principal)*

## 🎯 Objetivo da etapa

Entender e controlar modelos de geração de imagem, de difusão a edição fina.

## 📁 Estrutura sugerida da pasta

```
05-geracao-de-imagem/
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

- [ ] Autoencoders, VAEs e GANs (histórico)
- [ ] Difusão: processo direto e inverso, scores
- [ ] Espaço latente e classifier-free guidance
- [ ] Flow matching
- [ ] U-Net vs. DiT
- [ ] Text encoders e CLIP
- [ ] ControlNet, IP-Adapter, LoRA, DreamBooth
- [ ] Inpainting, outpainting, upscaling
- [ ] Edição por instrução e consistência de personagem
- [ ] Workflows em ComfyUI
- [ ] Avaliação: FID, CLIPScore, avaliação humana
- [ ] Aspectos legais e éticos (direitos de imagem, marca d'água)

## ✅ Critérios de validação (capacidades)

Só marque se você consegue fazer **sem ajuda e sem copiar tutorial**. Ao marcar, anote a evidência (arquivo, link, relatório).

- [ ] Explico o processo de difusão com as equações essenciais  
  - Evidência: 
- [ ] Monto um workflow avançado no ComfyUI  
  - Evidência: 
- [ ] Treino uma LoRA própria e avalio o resultado  
  - Evidência: 
- [ ] Controlo composição com ControlNet ou equivalente  
  - Evidência: 
- [ ] Comparo modelos com critérios objetivos e subjetivos  
  - Evidência: 
- [ ] Reconheço limitações e vieses dos modelos  
  - Evidência: 

## 🛠️ Entregáveis obrigatórios

- [ ] Workflow documentado com controle fino  
  - Link/caminho: 
- [ ] LoRA treinada com dataset curado e relatório  
  - Link/caminho: 
- [ ] Comparativo de modelos com avaliação  
  - Link/caminho: 

## ❓ Perguntas de autoavaliação

Responda **de memória, em voz alta ou por escrito**, antes de consultar qualquer material. Depois confira e anote o que errou.

1. Por que difusão opera em espaço latente?
   - Resposta (sem consultar):

2. O que é classifier-free guidance?
   - Resposta (sem consultar):

3. Qual a diferença entre U-Net e DiT?
   - Resposta (sem consultar):

4. Como uma LoRA altera o comportamento do modelo?
   - Resposta (sem consultar):

5. Por que FID é uma métrica limitada?
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

