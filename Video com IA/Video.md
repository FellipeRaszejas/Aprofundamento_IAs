# Geração de Vídeo com IA

Este guia explica como a IA gera vídeo: a difusão espaço-temporal, as três abordagens de geração (texto, imagem e vídeo para vídeo) e os conceitos essenciais da "direção" de um vídeo por IA, como movimentos de câmera, taxa de quadros e física. O mapeamento completo dos elementos que podem ser descritos em um prompt de vídeo está no [Guia de Prompt de Vídeo](guia-de-prompt-de-video.md).

## Sumário

1. [Difusão Espaço-Temporal](#1-difusão-espaço-temporal)
   - [O Desafio do Tempo](#o-desafio-do-tempo)
   - [Coerência entre os Quadros](#coerência-entre-os-quadros)
2. [Abordagens de Geração de Vídeo](#2-abordagens-de-geração-de-vídeo)
   - [Text-to-Video (Texto para Vídeo)](#text-to-video-texto-para-vídeo)
   - [Image-to-Video (Imagem para Vídeo)](#image-to-video-imagem-para-vídeo)
   - [Video-to-Video (Vídeo para Vídeo)](#video-to-video-vídeo-para-vídeo)
3. [Conceitos e Parâmetros Essenciais na Direção de Vídeo por IA](#3-conceitos-e-parâmetros-essenciais-na-direção-de-vídeo-por-ia)
   - [Movimentos de Câmera (Camera Motion)](#movimentos-de-câmera-camera-motion)
   - [Taxa de Quadros (FPS)](#taxa-de-quadros-fps)
   - [Física e Interação (Simulações do Mundo Real)](#física-e-interação-simulações-do-mundo-real)
4. [Resumo](#4-resumo)

---

## 1. Difusão Espaço-Temporal

![Ilustração conceitual de uma figura humana feminina de perfil, com a cabeça e o corpo formados por muitas imagens menores interligadas por linhas, sobre fundo cinza](imagens/ia-figura-formada-por-quadros-de-imagens.jpg)

*Ilustração conceitual: uma figura composta por muitas imagens menores, ideia próxima à do vídeo como uma sequência de quadros.*

**Conceito:** a geração de vídeo estende a ideia dos modelos de difusão de imagem (veja o guia [Geração de Imagens com IA](../geracao-de-imagens-com-ia/README.md)): além do espaço (cada quadro), o modelo precisa tratar o **tempo** (a sequência de quadros).

**No dia a dia:** é como um caderninho de desenho animado (*flipbook*). Cada página é uma imagem. Para a animação funcionar ao folhear, cada página precisa "lembrar" da anterior: o personagem não pode mudar de roupa ou de lugar sem motivo.

### O Desafio do Tempo

Em uma imagem, a IA calcula pixels em altura (H) e largura (W). No vídeo, entra a terceira dimensão: o tempo, representado pela quantidade de quadros (T).

| | Imagem | Vídeo |
|---|---|---|
| **Dimensões** | Altura (H) × Largura (W) | Altura (H) × Largura (W) × Tempo (T) |
| **Quantidade de quadros** | 1 | Muitos (5 segundos a 24 FPS são 120 quadros) |
| **Principal dificuldade** | Qualidade e fidelidade ao prompt | Qualidade **e** coerência entre os quadros |

Isso obriga a existir uma espécie de **memória** do quadro anterior, para que o modelo não se perca e acabe produzindo um vídeo desconexo.

### Coerência entre os Quadros

Para que o movimento seja contínuo, os modelos usam estratégias para relacionar um quadro ao outro:

| Estratégia | O que faz |
|---|---|
| **Atenção temporal** | Camadas da rede neural que comparam os quadros entre si, para que o conteúdo de um dependa do que veio antes e depois |
| **Fluxo óptico** (*Optical Flow*) | Técnica que determina matematicamente para onde cada pixel se move entre dois quadros consecutivos, para manter a coesão do movimento |
| **Quadro de referência** | Uma imagem inicial (como no *Image-to-Video*) que ancora a aparência do vídeo |

---

## 2. Abordagens de Geração de Vídeo

| Abordagem | Entrada | Resultado |
|---|---|---|
| **Text-to-Video** | Só o texto | Cena animada criada do zero |
| **Image-to-Video** | Uma imagem + texto | Imagem animada |
| **Video-to-Video** | Um vídeo + texto | Vídeo transformado |

### Text-to-Video (Texto para Vídeo)

Você escreve um prompt detalhado do zero e a IA cria a cena animada inteira. Exemplos de ferramentas: Sora (OpenAI), Runway Gen-3, Luma Dream Machine e Kling AI. A oferta de ferramentas muda com frequência, então vale conferir quais estão disponíveis no momento.

### Image-to-Video (Imagem para Vídeo)

Você fornece uma imagem estática (por exemplo, gerada por Midjourney ou DALL-E) e a usa como o "primeiro quadro" (*First Frame*), instruindo a IA a animar aquela imagem específica.

![Ilustração em estilo anime de uma personagem de cabelo azul curto, com óculos de aviador dourados e jaqueta laranja, diante de uma cidade de prédios antigos com visual steampunk](imagens/personagem-anime-steampunk-primeiro-frame.jpg)

*Exemplo de imagem estática que poderia servir de primeiro quadro: o prompt de vídeo descreveria apenas o movimento (por exemplo, a personagem virando o rosto e o vento mexendo no cabelo).*

### Video-to-Video (Vídeo para Vídeo)

Você grava um vídeo real, até mesmo com a câmera de um celular simples, e a IA substitui os pixels, transformando atores reais em personagens de anime, robôs de metal ou pinturas a óleo. O resultado não costuma ser em tempo real: o vídeo é processado e entregue depois.

![Comparação lado a lado de uma mesma rua de cidade: à esquerda, a cena com cores sóbrias; à direita, a cena estilizada com cores vibrantes e um grande redemoinho colorido no céu](imagens/transformacao-de-estilo-antes-e-depois-rua.jpg)

*Exemplo ilustrativo de transformação de estilo: à esquerda, a cena original; à direita, a mesma cena estilizada. No vídeo, a transformação precisa se manter coerente em todos os quadros.*

---

## 3. Conceitos e Parâmetros Essenciais na Direção de Vídeo por IA

**Conceito:** o mesmo mapeamento feito para imagens vale para o vídeo, com acréscimos: movimento de câmera, tempo, ritmo e física. O detalhamento completo está no [Guia de Prompt de Vídeo](guia-de-prompt-de-video.md).

### Movimentos de Câmera (Camera Motion)

Como a IA não tem uma câmera física, é preciso descrever ou parametrizar o movimento do ponto de vista virtual.

**No dia a dia:** é como dirigir uma filmagem. Você diz ao operador de câmera se ele deve girar no lugar, se aproximar ou acompanhar o ator andando.

| Movimento | Descrição |
|---|---|
| **Pan** (panorâmica) | A câmera gira horizontalmente para a esquerda ou para a direita, como olhar para os lados |
| **Tilt** | A câmera se inclina para cima ou para baixo, como olhar para o céu ou para o chão |
| **Zoom In / Zoom Out** | Aproximação ou afastamento, rápido ou lento, do sujeito central |
| **Tracking / Dolly Shot** | A câmera viaja fisicamente, acompanhando o movimento do sujeito |
| **Drone Shot / FPV** | Perspectiva aérea ampla, simulando um drone em movimento veloz |

### Taxa de Quadros (FPS)

**Conceito:** a taxa de quadros (*frames per second*, FPS) define a suavidade do movimento. As IAs de vídeo costumam gerar entre 24 e 30 FPS, sendo 24 FPS o padrão cinematográfico de Hollywood. O valor exato varia de ferramenta para ferramenta.

Movimentos rápidos em taxas baixas podem causar efeito "fantasma" ou distorção temporal.

### Física e Interação (Simulações do Mundo Real)

Os modelos avançados tentam imitar leis físicas reais, embora ainda possam falhar em detalhes complexos.

| Situação | O que se espera do modelo |
|---|---|
| **Colisões e gravidade** | Como objetos caem, batem ou espirram líquido |
| **Deformação de superfícies** | Como roupas dobram sobre o corpo ou como a água ondula ao toque |

---

## 4. Resumo

| Conceito | Ideia central |
|---|---|
| **Difusão espaço-temporal** | Difusão de imagem + a dimensão do tempo (T) |
| **Coerência entre quadros** | Memória do quadro anterior, atenção temporal e, em alguns casos, fluxo óptico |
| **Text-to-Video** | Do texto para a cena animada inteira |
| **Image-to-Video** | Anima uma imagem usada como primeiro quadro |
| **Video-to-Video** | Transforma um vídeo real em outro estilo |
| **Movimentos de câmera** | Pan, tilt, zoom, tracking/dolly, drone/FPV |
| **FPS** | 24 FPS é o padrão de cinema; 30 FPS é comum em vídeo |
| **Física** | Colisões, gravidade e deformação de superfícies, com falhas possíveis em detalhes complexos |