# Guia do Universo da IA: mapa de áreas para aprofundamento

*Para consultar depois de concluir os fundamentos. Aqui estão todas as grandes áreas da IA, inclusive as que mudam rápido (código, imagem, vídeo, áudio etc.).*

## Como usar este guia

Cada área traz quatro blocos:

- **O que é**: resumo de uma linha.
- **Fundamentos duráveis** 🧱: o que você aprende uma vez e vale por anos.
- **Tópicos e técnicas** 🔄: o que existe hoje, mas evolui rápido.
- **Ferramentas e exemplos** 🔄: nomes de produtos e modelos. **Estes mudam a cada poucos meses.** Trate-os como pontos de partida e sempre confirme o que está vigente antes de estudar.

**Regra de ouro:** aprenda o 🧱 profundamente, o 🔄 de forma prática, e nunca decore nomes de ferramentas. Decore o *problema que cada ferramenta resolve*.

---

## PARTE 1: IA GENERATIVA E CRIATIVA

### 1. Linguagem e texto (LLMs)

**O que é:** modelos que entendem e geram texto, a base de assistentes, agentes e a maioria dos produtos atuais.

- 🧱 Transformer, atenção, tokenização, funções de perda, scaling laws, decodificação (greedy, sampling, temperatura, top-p).
- 🔄 Pré-treino, fine-tuning (SFT, LoRA, QLoRA), alinhamento (RLHF, DPO, GRPO, recompensas verificáveis), modelos de raciocínio, destilação, Mixture of Experts, contexto longo, modelos pequenos (SLMs), modelos abertos vs. fechados.
- 🔄 Famílias de modelos: Claude, GPT, Gemini, Llama, Qwen, Mistral, DeepSeek e outras. A lista muda constantemente.
- **Como se aprofundar:** implemente um mini-GPT do zero, depois faça fine-tuning de um modelo aberto e meça o resultado.

### 2. Context Engineering, prompts e RAG

**O que é:** a arte de dar ao modelo o contexto certo (instruções, exemplos, documentos, memória, ferramentas) para obter resultados confiáveis.

- 🧱 Como o contexto afeta a geração, limites da janela de contexto, avaliação sistemática.
- 🔄 Prompting (zero/few-shot, CoT, ReAct), structured outputs, RAG (chunking, busca híbrida, re-ranking, GraphRAG, RAG agêntico), cache de prompt, compressão de contexto, memória de longo prazo.
- 🔄 Ferramentas: LangChain, LlamaIndex, DSPy, bancos vetoriais (Qdrant, Milvus, pgvector, Pinecone), Langfuse, LangSmith.
- **Habilidade-chave:** construir um conjunto de avaliação antes de otimizar qualquer prompt.

### 3. Agentes de IA e automação

**O que é:** sistemas em que o modelo planeja, usa ferramentas e executa tarefas em múltiplos passos.

- 🧱 Planejamento, ciclo observar-pensar-agir, tratamento de erros, noções de aprendizado por reforço.
- 🔄 Function calling, MCP (Model Context Protocol), sistemas multiagente, memória, agentes que usam computador/navegador, orquestração de fluxos (LangGraph, CrewAI, AutoGen), SDKs de agentes dos grandes laboratórios, automação com n8n e Zapier.
- 🔄 Avaliação de agentes: taxa de sucesso em tarefas longas, custo por tarefa, confiabilidade, segurança (prompt injection).
- **Cuidado:** agentes falham de formas sutis. Aprender a *avaliar e limitar* agentes vale mais que aprender a criá-los.

### 4. Desenvolvimento de código com IA

**O que é:** IA que escreve, revisa, depura, testa e refatora software.

- 🧱 Engenharia de software sólida (arquitetura, testes, revisão de código). Sem isso você não consegue avaliar o que a IA gera.
- 🔄 Autocomplete, chat em IDE, agentes de código que editam repositórios inteiros, revisão automática de PRs, geração de testes, migração de código legado, "vibe coding" (e seus riscos).
- 🔄 Ferramentas: Claude Code, Cursor, GitHub Copilot, Codex, Windsurf, Cline, entre outras.
- 🔄 Avaliação: SWE-bench, HumanEval, LiveCodeBench e benchmarks parecidos.
- 🔄 Como treinar modelos de código: dados de repositórios, aprendizado com execução e testes como recompensa.
- **Habilidade-chave:** especificar bem a tarefa, revisar criticamente, escrever bons testes e conhecer os limites da ferramenta.

### 5. Geração de imagem

**O que é:** criar e editar imagens a partir de texto, referências ou outras imagens.

- 🧱 Autoencoders, VAEs, GANs (histórico), difusão (processo direto/inverso, scores), espaço latente, guidance (classifier-free), flow matching, noções de CLIP e text encoders.
- 🔄 Arquiteturas: U-Net, DiT (Diffusion Transformers), modelos autorregressivos de imagem.
- 🔄 Controle fino: ControlNet, IP-Adapter, LoRAs, DreamBooth, inpainting/outpainting, upscaling, edição por instrução, consistência de personagem.
- 🔄 Ferramentas: Stable Diffusion, Flux, Midjourney, DALL·E / modelos de imagem integrados a LLMs, Imagen, Adobe Firefly, ComfyUI e Automatic1111 (interfaces de fluxo).
- **Como se aprofundar:** monte workflows no ComfyUI, treine uma LoRA própria e estude como avaliar qualidade (FID, CLIPScore, avaliação humana).

### 6. Geração de vídeo

**O que é:** criar vídeo a partir de texto, imagem ou outro vídeo, com coerência temporal.

- 🧱 Difusão aplicada ao tempo, representação espaço-temporal, atenção temporal, noções de compressão de vídeo (VAEs de vídeo).
- 🔄 Texto-para-vídeo, imagem-para-vídeo, vídeo-para-vídeo, controle de câmera, consistência de personagem e cena, animação (AnimateDiff e similares), lip-sync, vídeo com áudio nativo, edição de vídeo por IA.
- 🔄 Ferramentas: Sora, Veo, Runway, Kling, Luma, Pika, Wan (aberto), entre outras.
- 🔄 Desafios abertos: física plausível, duração longa, custo computacional, consistência.
- **Pipeline típico profissional:** roteiro, storyboard, geração de cenas, edição, som, pós-produção. As ferramentas de IA entram em cada etapa.

### 7. Áudio, voz e música

**O que é:** reconhecer, sintetizar e gerar som.

- 🧱 Processamento de sinais (Fourier, espectrogramas, mel), codecs de áudio, noções de acústica.
- 🔄 Reconhecimento de fala (Whisper e sucessores), síntese de voz (TTS), clonagem de voz (com ética e consentimento), tradução de fala em tempo real, agentes de voz de baixa latência, geração de música e efeitos sonoros, separação de fontes, codecs neurais.
- 🔄 Ferramentas: Whisper, ElevenLabs, Suno, Udio, entre outras.
- **Atenção:** áreas com forte impacto legal (direitos de voz e de autor) e risco de deepfake.

### 8. 3D, mundos e simulação

**O que é:** gerar ou reconstruir cenas e objetos tridimensionais e simular ambientes.

- 🧱 Geometria, câmeras, renderização, representações 3D (malhas, nuvens de pontos, campos implícitos).
- 🔄 NeRF, Gaussian Splatting, geração de objetos 3D por texto/imagem, modelos de mundo (world models), geração de cenários interativos, gêmeos digitais, jogos e simulação.
- **Conexão:** world models são ponte direta para robótica e para a pesquisa de fronteira.

### 9. Multimodalidade

**O que é:** modelos que combinam texto, imagem, áudio e vídeo no mesmo sistema.

- 🧱 Alinhamento de representações entre modalidades, aprendizado contrastivo (CLIP).
- 🔄 VLMs (modelos visão-linguagem), modelos nativamente multimodais, entendimento de documentos/OCR, análise de vídeo, modelos omni (voz+visão em tempo real), modelos de ação (VLAs).

---

## PARTE 2: IA PERCEPTIVA E ANALÍTICA

### 10. Visão computacional

- 🧱 Convoluções, geometria de imagem, noções de câmera.
- 🔄 Classificação, detecção (YOLO e sucessores), segmentação (SAM e similares), rastreamento, estimativa de pose, OCR, reconhecimento facial (com forte debate ético e legal), visão em borda (câmeras, drones), inspeção industrial, imagens médicas e de satélite, Vision Transformers.

### 11. Dados, analytics e ciência de dados

- 🧱 Estatística, experimentação (testes A/B), inferência causal, modelagem.
- 🔄 ML tabular (boosting continua forte), séries temporais e previsão (incluindo modelos fundacionais para séries), detecção de anomalias, sistemas de recomendação, text-to-SQL e BI com IA, AutoML, engenharia de features automatizada.

### 12. Busca e recuperação de informação

- 🧱 Indexação, relevância, métricas (nDCG, MRR).
- 🔄 Embeddings, busca semântica e híbrida, learning to rank, grafos de conhecimento, busca generativa, recomendação em escala.

### 13. Processamento de linguagem natural aplicado

- 🔄 Classificação e extração de informação, resumo, tradução, análise de sentimento, moderação de conteúdo, NLP em português e línguas de poucos recursos, extração de dados de documentos (contratos, notas fiscais, laudos).

---

## PARTE 3: IA NO MUNDO FÍSICO E NA CIÊNCIA

### 14. Robótica e IA incorporada (embodied AI)

- 🧱 Cinemática, controle, percepção, aprendizado por reforço, simulação.
- 🔄 Aprendizado por imitação, modelos visão-linguagem-ação (VLAs), robôs humanoides, manipulação, sim-to-real, navegação, drones, veículos autônomos (fusão de sensores, LiDAR).

### 15. IA para ciência e engenharia

- 🔄 Biologia e proteínas (AlphaFold e sucessores), descoberta de fármacos, genômica, química e materiais, clima e meteorologia, física (surrogates de simulação, PINNs), matemática (prova assistida), agentes de pesquisa científica.

### 16. IA por setor (cada um exige conhecimento do domínio)

- **Saúde:** diagnóstico por imagem, prontuários, regulamentação (ANVISA, FDA).
- **Finanças:** risco de crédito, fraude, negociação, regulação (Banco Central, CVM).
- **Jurídico:** análise de contratos, jurisprudência, riscos de alucinação.
- **Educação:** tutores personalizados, avaliação, integridade acadêmica.
- **Indústria e agro:** manutenção preditiva, visão em linha de produção, agricultura de precisão.
- **Varejo, marketing e atendimento:** personalização, agentes de atendimento, geração de conteúdo.
- **Governo e setor público:** serviços digitais, LGPD, transparência.

---

## PARTE 4: SISTEMAS, INFRAESTRUTURA E PRODUÇÃO

### 17. Hardware e programação de baixo nível

- 🧱 Arquitetura de computadores, hierarquia de memória, paralelismo.
- 🔄 GPUs, TPUs, NPUs, CUDA, Triton (a linguagem de kernels), compiladores de ML (torch.compile, XLA, MLIR), FlashAttention por dentro, interconexões (NVLink, InfiniBand), HBM, aceleradores especializados.

### 18. Treinamento e inferência em escala

- 🧱 Paralelismo de dados, de tensor e de pipeline.
- 🔄 FSDP, DeepSpeed, Megatron, mixed precision (FP8/FP4), quantização (GGUF, AWQ, GPTQ), speculative decoding, continuous batching, PagedAttention, KV-cache, servidores de inferência (vLLM, TGI, SGLang, Triton Inference Server, Ollama).

### 19. MLOps e LLMOps

- 🧱 Reprodutibilidade, versionamento, monitoramento, CI/CD.
- 🔄 Rastreamento de experimentos (MLflow, W&B), pipelines, feature stores, observabilidade de LLMs, guardrails, roteamento de modelos, caching, FinOps de IA, nuvens (SageMaker, Vertex AI, Azure AI, Bedrock), Kubernetes, Ray.

### 20. IA em borda e dispositivos (Edge AI / TinyML)

- 🔄 Modelos em celular, navegador (WebGPU) e microcontroladores, quantização agressiva, privacidade on-device.

---

## PARTE 5: CONFIABILIDADE, SEGURANÇA E SOCIEDADE

### 21. Avaliação (evals)

- 🧱 Estatística de comparação, design de experimentos, construção de datasets de teste.
- 🔄 Benchmarks (MMLU, GPQA, SWE-bench, entre outros), contaminação de benchmarks, LLM-as-a-Judge e seus vieses, avaliação humana, avaliação de agentes, red teaming, métricas de RAG (Ragas).
- **Habilidade mais subestimada:** criar avaliações próprias para o seu problema.

### 22. Segurança, alinhamento e interpretabilidade

- 🧱 Ataques adversariais, noções de teoria de jogos e de incentivos.
- 🔄 Prompt injection, jailbreaks, envenenamento de dados, vazamento de dados, privacidade (differential privacy, federated learning), supervisão escalável, avaliação de capacidades perigosas, **interpretabilidade mecanística** (circuitos, probing, sparse autoencoders), explicabilidade (SHAP, LIME), segurança de agentes.

### 23. Ética, viés, governança e regulação

- 🔄 Fairness e viés, transparência, direitos autorais e dados de treino, deepfakes e desinformação, impacto no trabalho, AI Act (UE), LGPD e o marco regulatório brasileiro de IA (acompanhe a tramitação), normas como ISO/IEC 42001 e NIST AI RMF.

---

## PARTE 6: PESQUISA DE FRONTEIRA (para quem quer ir além)

- 🧱 Teoria do aprendizado, otimização, generalização.
- 🔄 Arquiteturas pós-Transformer (State Space Models, híbridos), difusão para texto, JEPA e aprendizado de representações, treino com recompensas verificáveis, escala em tempo de teste, aprendizado contínuo, meta-learning, dados sintéticos, agentes de longo prazo, auto-aperfeiçoamento, IA neuro-simbólica, computação neuromórfica e quântica (incipientes).

---

## PARTE 7: PRODUTO, NEGÓCIO E CARREIRA

- **Quando usar IA e quando não usar**: muitos problemas se resolvem melhor com regras ou estatística simples.
- **Traduzir negócio em problema técnico**, definir métricas e medir ROI.
- **Design de produtos com IA**: UX para incerteza, feedback humano, fallback, confiança do usuário.
- **Custos**: latência vs. qualidade vs. custo, escolha de modelo, otimização de gastos.
- **Comunicação e liderança técnica**: documentação, decisões de arquitetura (ADRs), mentoria.
- **Empreendedorismo e consultoria em IA**: nichos, produtos verticais, venda de soluções.

---

## COMO ACOMPANHAR O QUE MUDA

Como as partes 🔄 envelhecem rápido, crie uma rotina em vez de uma lista fixa:

- **Papers:** arXiv (cs.LG, cs.CL, cs.CV, cs.AI), Hugging Face Daily Papers, Papers with Code.
- **Modelos e ferramentas abertas:** Hugging Face, GitHub, comunidades como r/LocalLLaMA.
- **Blogs técnicos oficiais** dos grandes laboratórios e empresas de infraestrutura.
- **Conferências:** NeurIPS, ICML, ICLR, CVPR, ACL, EMNLP (leia os papers premiados e os tutoriais).
- **Cursos de referência:** Stanford (CS229, CS231n, CS224n, CS336), fast.ai, Andrej Karpathy (Neural Networks: Zero to Hero), DeepLearning.AI.
- **Rotina sugerida:** 1 paper por semana, 1 experimento prático por mês, 1 projeto público por trimestre.

---

## COMO ESCOLHER SUA TRILHA DEPOIS DOS FUNDAMENTOS

Um caminho comum é **base ampla + 1 ou 2 áreas profundas**. Algumas combinações naturais:

- **Engenheiro de LLMs e agentes:** Áreas 1, 2, 3, 4, 21, 19.
- **Especialista em mídia generativa:** Áreas 5, 6, 7, 8, 9.
- **Pesquisador / cientista aplicado:** Áreas 1, 18, 21, 22 e Parte 6.
- **Engenheiro de ML / MLOps:** Áreas 11, 18, 19, 20, 17.
- **IA aplicada a um setor:** a Área 16 correspondente, mais 2 e 21.
- **Robótica:** Áreas 14, 10, 8, 9.
- **Segurança e confiabilidade de IA:** Áreas 21, 22, 23.

**Critério de escolha:** o que você consegue *construir e mostrar* com o que gosta de fazer, e onde há demanda real no mercado em que você quer atuar.

---

## Checklist final: você está pronto para escolher a especialização quando...

- Implementou uma rede neural do zero e um mini-GPT.
- Consegue ler um paper e reproduzir os resultados principais.
- Sabe montar um conjunto de avaliação e comparar modelos com rigor estatístico.
- Colocou pelo menos um modelo ou sistema com LLM em produção, com monitoramento.
- Tem 3 ou mais projetos públicos documentados.
- Sabe explicar o *porquê* das técnicas, não só usá-las.
