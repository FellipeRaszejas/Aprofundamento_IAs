# Geração de Imagens com IA

Este guia explica como a IA transforma texto em imagem: o princípio da difusão, a ponte entre linguagem e pixels, os conceitos essenciais (prompt visual, espaço latente e ControlNet) e as questões de governança envolvidas. O detalhamento de estilos, paletas, proporções, lentes e demais elementos do prompt está no [Guia de Prompt Visual](guia-de-prompt-visual.md).

## Sumário

1. [Como Funciona a Tecnologia? (O Princípio da Difusão)](#1-como-funciona-a-tecnologia-o-princípio-da-difusão)
   - [A Fase de Ruído (Forward Diffusion)](#a-fase-de-ruído-forward-diffusion)
   - [A Fase de Denoising (Reverse Diffusion)](#a-fase-de-denoising-reverse-diffusion)
2. [A Ponte entre Texto e Imagem (Text-to-Image)](#2-a-ponte-entre-texto-e-imagem-text-to-image)
3. [Conceitos Essenciais na Geração de Imagens](#3-conceitos-essenciais-na-geração-de-imagens)
   - [Prompt Engineering Visual](#prompt-engineering-visual)
   - [Latent Space (Espaço Latente)](#latent-space-espaço-latente)
   - [ControlNet e Controles de Estrutura](#controlnet-e-controles-de-estrutura)
4. [Onde Isso se Conecta com a Governança e os Agentes](#4-onde-isso-se-conecta-com-a-governança-e-os-agentes)
5. [Resumo](#5-resumo)

---

## 1. Como Funciona a Tecnologia? (O Princípio da Difusão)

**Conceito:** a grande maioria das ferramentas modernas de geração de imagem baseia-se em uma arquitetura chamada **Modelos de Difusão** (*Diffusion Models*). O Stable Diffusion é o exemplo mais documentado; outras ferramentas, como Midjourney e DALL-E, costumam ser descritas da mesma forma, embora nem todas divulguem sua arquitetura completa.

**No dia a dia:** imagine um desenho coberto aos poucos por areia fina até sumir por completo. Agora imagine alguém que aprendeu a fazer o caminho inverso: dado um monte de areia, ele a varre aos poucos e revela um desenho. É isso que o modelo aprende a fazer, com milhares de exemplos.

O funcionamento conceitual divide-se em duas fases:

| Fase | Quando acontece | O que faz | Resultado |
|---|---|---|---|
| **Ruído** (*Forward Diffusion*) | Durante o treinamento | Adiciona ruído progressivamente a imagens reais | Imagem irreconhecível |
| **Denoising** (*Reverse Diffusion*) | Na geração, quando o usuário pede uma imagem | Remove o ruído passo a passo, guiado pelo prompt | Imagem final nítida |

### A Fase de Ruído (Forward Diffusion)

Durante o treinamento, o modelo pega milhares de imagens reais e adiciona progressivamente camadas de "ruído" (estática, como a de uma televisão antiga) até que a imagem se torne completamente irreconhecível.

| 🖼️ Imagem real | → | 🌫️ Pouco ruído | → | 🌨️ Muito ruído | → | 📺 Ruído total |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|

### A Fase de Denoising (Reverse Diffusion)

O modelo aprende o caminho inverso. Ele recebe uma tela cheia de ruído aleatório e, guiado pelo texto (o *prompt*), remove o ruído passo a passo até esculpir a imagem final, nítida, que corresponde ao pedido.

| 📺 Ruído aleatório + prompt | → | 🌨️ Formas vagas | → | 🌫️ Detalhes surgindo | → | 🖼️ Imagem final nítida |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|

---

## 2. A Ponte entre Texto e Imagem (Text-to-Image)

**Conceito:** para entender o que desenhar a partir de palavras, a IA precisa cruzar dois mundos: o **linguístico** (texto) e o **visual** (pixels).

**No dia a dia:** é como um intérprete entre dois idiomas. O texto do usuário é traduzido para uma "língua dos números", que a rede neural consegue seguir ao desenhar.

| Peça | O que faz |
|---|---|
| **Modelo de linguagem embutido** | Um modelo auxiliar (como o CLIP, desenvolvido pela OpenAI) lê o texto e o traduz para um espaço vetorial, uma representação numérica do significado das palavras |
| **Guia de estilo e semântica** | Durante o *denoising*, esses vetores numéricos dizem à rede neural o que fazer, por exemplo: "Mantenha as formas parecidas com um gato", "Adicione iluminação de estúdio" ou "Pinte com estilo cyberpunk" |

---

## 3. Conceitos Essenciais na Geração de Imagens

### Prompt Engineering Visual

**Conceito:** assim como nos chats, a forma como você descreve a imagem altera o resultado. Um prompt visual inclui o sujeito, o contexto, a iluminação, a paleta de cores, a proporção e a referência a estilos artísticos ou lentes fotográficas.

**No dia a dia:** é como encomendar um bolo. "Um bolo" gera uma surpresa; "bolo de chocolate, dois andares, cobertura branca, para aniversário infantil" gera o que você imaginou.

| Elemento | O que descreve | Exemplo |
|---|---|---|
| **Sujeito** | Quem ou o que aparece | Um astronauta |
| **Contexto** | Onde e quando | Na superfície da lua |
| **Iluminação** | Como a cena é iluminada | Luz de estúdio |
| **Paleta de cores** | Cores dominantes | Tons frios, azul e prata |
| **Proporção** | Formato da imagem | 16:9 |
| **Estilo** | Linguagem visual | Cyberpunk |
| **Lente** | Efeito fotográfico | Grande angular |

> Todas as opções de cada elemento (lista de estilos, paletas, proporções, lentes, ângulos e muito mais) estão no [Guia de Prompt Visual](guia-de-prompt-visual.md).

### Latent Space (Espaço Latente)

**Conceito:** é o "oceano matemático" onde a IA guarda conceitos visuais. Quando o pedido mistura duas ideias (por exemplo, "um astronauta cavalgando um cavalo na lua"), a IA navega pelo espaço latente e encontra o meio-termo matemático entre esses conceitos.

**No dia a dia:** é como misturar tintas. Azul e amarelo, combinados na proporção certa, dão um verde; a IA faz algo parecido com conceitos, e não com cores.

Em modelos como o Stable Diffusion, o próprio *denoising* acontece nesse espaço comprimido, e só no final um decodificador converte o resultado em pixels. Isso torna a geração muito mais leve do que trabalhar diretamente sobre cada pixel.

### ControlNet e Controles de Estrutura

**Conceito:** são extensões arquiteturais que permitem controlar a posição, as linhas de rascunho ou a pose de uma figura humana gerada, garantindo precisão técnica muito além de um simples texto solto.

**No dia a dia:** é como usar um molde ou um papel de decalque. O texto diz *o que* desenhar; o molde diz *onde* cada coisa fica.

---

## 4. Onde Isso se Conecta com a Governança e os Agentes

A geração de imagens também passa pelos pilares apresentados no guia de [Governança de IA](../governanca-de-ia/README.md):

| Tema | Preocupação | Relação com a governança |
|---|---|---|
| **Direitos autorais e propriedade intelectual** | Como os modelos foram treinados com bilhões de imagens da internet, há grandes debates globais sobre conformidade legal, *copyright* e artistas cujos estilos foram replicados sem consentimento | Gestão de risco e conformidade |
| **Guardrails e segurança** | As plataformas aplicam filtros rigorosos para impedir conteúdos falsos prejudiciais (*deepfakes*), imagens de violência, conteúdo adulto ou representações enganosas de figuras públicas | Alinhamento e comportamento (*Safety & Alignment*) |

A geração visual é, portanto, a evolução lógica da IA: em vez de apenas prever texto, ela aprendeu a traduzir a imaginação humana, estruturada em texto, para representações gráficas complexas.

---

## 5. Resumo

| Conceito | Ideia central |
|---|---|
| **Modelo de difusão** | Aprende a adicionar e a remover ruído de imagens |
| **Forward Diffusion** | Treinamento: imagem real vira ruído |
| **Reverse Diffusion** | Geração: ruído vira imagem, guiado pelo prompt |
| **Text-to-Image** | Um modelo auxiliar (como o CLIP) converte o texto em vetores que guiam o *denoising* |
| **Prompt visual** | Sujeito, contexto, iluminação, paleta, proporção, estilo e lente |
| **Espaço latente** | "Oceano matemático" onde os conceitos visuais ficam guardados |
| **ControlNet** | Controle de posição, rascunho e pose |
| **Governança** | Direitos autorais e *guardrails* de segurança |