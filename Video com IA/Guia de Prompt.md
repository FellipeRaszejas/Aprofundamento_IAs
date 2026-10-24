# Guia de Prompt de Vídeo

Este guia reúne, em forma de consulta, os elementos que podem ser descritos em um prompt de geração de vídeo por IA: tipos de geração, sujeito e ação, movimentos de câmera, duração e taxa de quadros, estilo, cor, proporção, física, consistência, controles e problemas comuns. Ele complementa o [README principal](README.md) e parte do mapeamento já feito para imagens, no [Guia de Prompt Visual](../geracao-de-imagens-com-ia/guia-de-prompt-visual.md).

## Sumário

1. [Anatomia de um Prompt de Vídeo](#1-anatomia-de-um-prompt-de-vídeo)
2. [Tipos de Geração de Vídeo](#2-tipos-de-geração-de-vídeo)
3. [Sujeito e Ação](#3-sujeito-e-ação)
4. [Contexto e Cenário](#4-contexto-e-cenário)
5. [Movimentos de Câmera](#5-movimentos-de-câmera)
6. [Enquadramento, Ângulo e Lente](#6-enquadramento-ângulo-e-lente)
7. [Duração, Ritmo e Taxa de Quadros](#7-duração-ritmo-e-taxa-de-quadros)
8. [Estilo e Estética](#8-estilo-e-estética)
9. [Iluminação e Cor](#9-iluminação-e-cor)
10. [Proporção e Resolução](#10-proporção-e-resolução)
11. [Física e Interação](#11-física-e-interação)
12. [Consistência de Personagens e Cenários](#12-consistência-de-personagens-e-cenários)
13. [Controles e Parâmetros](#13-controles-e-parâmetros)
14. [Problemas Comuns](#14-problemas-comuns)
15. [Cuidados e Governança](#15-cuidados-e-governança)
16. [Montando um Prompt Completo](#16-montando-um-prompt-completo)

---

## 1. Anatomia de um Prompt de Vídeo

**Conceito:** um prompt de vídeo tem as mesmas camadas de um prompt de imagem, acrescidas de **movimento**, **câmera** e **tempo**. Em imagem, você descreve uma cena parada; em vídeo, descreve o que acontece nela.

**No dia a dia:** é como escrever a instrução para uma cena de filme. Além de "onde e quem", você diz o que o ator faz, como a câmera se move e quanto tempo dura a cena.

| Camada | Pergunta que responde | Seção |
|---|---|---|
| **Sujeito e ação** | Quem ou o que aparece e o que faz? | [3](#3-sujeito-e-ação) |
| **Contexto** | Onde, quando e em que clima? | [4](#4-contexto-e-cenário) |
| **Câmera** | Como o ponto de vista se move? | [5](#5-movimentos-de-câmera) |
| **Enquadramento e lente** | De onde e com que efeito a cena é vista? | [6](#6-enquadramento-ângulo-e-lente) |
| **Tempo** | Quanto dura e em que ritmo? | [7](#7-duração-ritmo-e-taxa-de-quadros) |
| **Estilo** | Qual a linguagem visual? | [8](#8-estilo-e-estética) |
| **Luz e cor** | Como a luz e as cores se comportam? | [9](#9-iluminação-e-cor) |
| **Formato** | Proporção e resolução | [10](#10-proporção-e-resolução) |

---

## 2. Tipos de Geração de Vídeo

| Tipo | O que faz | Entrada |
|---|---|---|
| **Texto para vídeo** (*text-to-video*) | Cria a cena animada do zero | Só o texto |
| **Imagem para vídeo** (*image-to-video*) | Anima uma imagem estática | Imagem + texto |
| **Quadro inicial e final** | Cria o movimento entre duas imagens | Duas imagens + texto |
| **Vídeo para vídeo** (*video-to-video*) | Transforma um vídeo existente (estilo, personagens, cenário) | Vídeo + texto |
| **Extensão de vídeo** | Continua um clipe além do final | Vídeo + texto |
| **Transferência de movimento** | Aplica o movimento de um vídeo a outro personagem | Vídeo de movimento + imagem do personagem |
| **Sincronia labial** (*lip sync*) | Faz um rosto falar de acordo com um áudio | Vídeo ou imagem + áudio |
| **Edição de vídeo** | Remove, troca ou altera objetos em um vídeo | Vídeo + texto ou máscara |
| **Ampliação e interpolação** | Aumenta a resolução ou cria quadros extras para mais suavidade | Vídeo |

> A disponibilidade desses recursos varia de ferramenta para ferramenta e muda com o tempo.

---

## 3. Sujeito e Ação

**Conceito:** em vídeo, o sujeito precisa de uma **ação**. O verbo é a parte mais importante do prompt.

| Elemento | O que descrever | Exemplos |
|---|---|---|
| **Sujeito** | Aparência, roupa, idade aproximada (veja o [guia de imagem](../geracao-de-imagens-com-ia/guia-de-prompt-visual.md#3-sujeito)) | Uma mulher de jaqueta laranja |
| **Ação principal** | O que o sujeito faz | Caminha, corre, vira o rosto, acena, dança |
| **Velocidade** | Ritmo do movimento | Lento, constante, rápido, explosivo |
| **Direção** | Para onde se move | Em direção à câmera, da esquerda para a direita, para o horizonte |
| **Intensidade** | Força do movimento | Sutil, moderado, exagerado |
| **Ações secundárias** | Detalhes que dão vida | Vento no cabelo, piscar de olhos, folhas caindo |

Dicas:

| Faça | Evite |
|---|---|
| Uma ação principal clara por clipe | Várias ações em sequência dentro de poucos segundos |
| Verbos concretos ("caminha lentamente") | Termos vagos ("faz algo legal") |
| Movimentos que a cena torna plausíveis | Ações fisicamente complexas, com muitos elementos interagindo |

---

## 4. Contexto e Cenário

Os elementos de contexto de imagem (local, ambiente, época, hora do dia, estação, clima e fundo) valem também para vídeo. O que muda é que o cenário pode **evoluir ao longo do clipe**.

| Elemento de vídeo | Exemplos |
|---|---|
| **Mudança de luz ao longo do tempo** | Do amanhecer ao dia pleno, do dia para a noite |
| **Mudança de clima** | A chuva começa a cair, a névoa se dissipa |
| **Elementos em movimento no fundo** | Pessoas passando, carros, nuvens, folhas ao vento |
| **Cenário estático ou dinâmico** | Rua vazia ou movimentada |

---

## 5. Movimentos de Câmera

**Conceito:** como a IA não tem uma câmera física, é preciso descrever o movimento do ponto de vista virtual. Quanto mais específico o movimento (tipo, direção e velocidade), mais previsível o resultado.

| Movimento | Descrição | Efeito |
|---|---|---|
| **Estática** (*static / locked-off*) | A câmera não se move | Estabilidade, foco na ação do sujeito |
| **Pan** (panorâmica) | A câmera gira horizontalmente, para a esquerda ou para a direita | Revela o cenário ou acompanha algo |
| **Tilt** | A câmera inclina para cima ou para baixo | Mostra altura (prédio, céu) ou chão |
| **Zoom In / Zoom Out** | A lente aproxima ou afasta, sem a câmera se mover | Aproximação ou afastamento rápido ou lento do sujeito |
| **Dolly In / Dolly Out** | A câmera avança em direção ao sujeito ou recua | Aproximação com mudança de perspectiva, mais imersiva que o zoom |
| **Tracking Shot** | A câmera acompanha o sujeito, de lado, à frente ou por trás | Sensação de acompanhar a ação |
| **Truck** | A câmera se desloca lateralmente, em linha reta | Revela o cenário de lado |
| **Pedestal / Crane** | A câmera sobe ou desce verticalmente | Revelação de escala, cenas grandiosas |
| **Orbit / Arc** | A câmera gira em torno do sujeito | Mostra o sujeito de vários ângulos |
| **Roll** | A câmera gira sobre o próprio eixo | Desorientação, efeito onírico |
| **Câmera na mão** (*handheld*) | Movimento leve e irregular | Realismo, aparência documental |
| **Drone Shot / FPV** | Perspectiva aérea ampla, simulando um drone em movimento veloz | Voo, grandiosidade, velocidade |
| **Whip Pan** | Panorâmica muito rápida, que borra a imagem | Transição brusca, energia |
| **Dolly Zoom** | Câmera se aproxima enquanto a lente afasta (ou o inverso) | Estranhamento, tensão (efeito "Vertigo") |

> Diferença importante: o **zoom** muda a lente e não a perspectiva; o **dolly** move a câmera e muda a perspectiva.

Combinações comuns: "dolly in lento com leve câmera na mão", "orbit em torno do personagem, com a câmera na altura dos olhos".

---

## 6. Enquadramento, Ângulo e Lente

Os conceitos de enquadramento (plano geral, médio, close-up), ângulo (contra-plongée, plongée, zenital, holandês, POV), composição e lente (grande angular, retrato, teleobjetiva, macro, profundidade de campo) são os mesmos do [Guia de Prompt Visual](../geracao-de-imagens-com-ia/guia-de-prompt-visual.md#9-enquadramento-ângulo-e-composição). Em vídeo, valem alguns acréscimos:

| Elemento | Descrição |
|---|---|
| **Plano-sequência** | Uma tomada contínua, sem cortes, acompanhando a cena |
| **Corte** | Troca de plano dentro do mesmo clipe (nem toda ferramenta lida bem com isso; costuma ser mais seguro gerar um plano por clipe e montar na edição) |
| **Mudança de foco** (*rack focus*) | O foco passa de um elemento para outro durante a cena |
| **Profundidade de campo** | Fundo desfocado para destacar o sujeito, ou tudo nítido |
| **Câmera lenta** | Ação mostrada mais devagar, para dar peso ou beleza |
| **Aceleração** (*time-lapse*) | Passagem de tempo acelerada (nuvens, trânsito, flores abrindo) |
| **Hiperlapse** | *Time-lapse* com a câmera em movimento |

---

## 7. Duração, Ritmo e Taxa de Quadros

**Conceito:** o tempo é a dimensão nova do vídeo. Ele envolve a duração do clipe, o ritmo da ação e a taxa de quadros.

### Duração

Os clipes gerados costumam ter de poucos segundos a algumas dezenas de segundos, dependendo da ferramenta. Clipes curtos tendem a ser mais coerentes; para cenas longas, o mais seguro é gerar vários clipes e uni-los na edição.

### Taxa de quadros (FPS)

| FPS | Sensação | Uso comum |
|---|---|---|
| **24** | Aparência de cinema | Filmes, séries, estilo cinematográfico |
| **25 e 30** | Vídeo "natural" | TV, vídeos na internet |
| **60** | Muito fluido | Esportes, jogos, ação rápida |
| **Mais de 60** | Base para câmera lenta | Efeitos de *slow motion* |

Movimentos rápidos em taxas baixas podem causar efeito "fantasma" ou distorção temporal. Muitas ferramentas geram em uma taxa fixa; nesse caso, a interpolação de quadros pode ser aplicada depois.

### Ritmo

| Pedido | Efeito |
|---|---|
| **Lento e contemplativo** | Calma, beleza, suspense |
| **Constante** | Neutro, narrativo |
| **Rápido e dinâmico** | Energia, ação |
| **Início, meio e fim** | Pequena narrativa dentro do clipe (use com moderação em clipes curtos) |

---

## 8. Estilo e Estética

Os estilos de imagem (2D, 3D, pintura, movimentos artísticos, cyberpunk, medieval, realismo etc.) estão no [Guia de Prompt Visual](../geracao-de-imagens-com-ia/guia-de-prompt-visual.md#5-estilo-e-categorias-visuais). Para vídeo, estas categorias de **formato audiovisual** se somam a eles:

| Categoria | Característica |
|---|---|
| **Cinematográfico (live action)** | Aparência de filme, com iluminação e câmera de cinema |
| **Documentário** | Câmera na mão, luz natural, aparência de registro real |
| **Comercial / publicidade** | Imagem polida, produto em destaque, movimentos suaves |
| **Videoclipe** | Cortes e movimentos estilizados, cores fortes |
| **Trailer** | Ritmo crescente, cenas épicas |
| **Animação 2D** | Desenho animado tradicional ou digital, anime |
| **Animação 3D** | Personagens e cenários renderizados em 3D |
| ***Stop motion*** | Aparência de quadro a quadro, com texturas de massinha ou papel |
| ***Motion graphics*** | Formas, textos e elementos gráficos animados |
| **Imagem de arquivo antigo** | Granulado, preto e branco, aparência de filme antigo |
| **VHS / retrô** | Cores desbotadas, ruído, aparência dos anos 1980 e 1990 |
| **Câmera de segurança / *found footage*** | Imagem tosca, sem enquadramento "bonito" |

---

## 9. Iluminação e Cor

A iluminação (hora dourada, luz de contorno, neon, volumétrica, *low-key* e *high-key*) e as paletas de cores estão no [Guia de Prompt Visual](../geracao-de-imagens-com-ia/guia-de-prompt-visual.md#6-iluminação). Em vídeo, acrescenta-se a **gradação de cor** (*color grading*), o tratamento de cor aplicado ao filme inteiro:

| Gradação | Efeito |
|---|---|
| **Azul-esverdeado e laranja** (*teal and orange*) | Visual de blockbuster, contraste entre pele e fundo |
| **Dessaturada** | Aparência fria, séria, realista |
| **Vívida e saturada** | Energia, alegria, publicidade |
| **Preto e branco** | Clássico, dramático |
| **Tons quentes e suaves** | Nostalgia, aconchego |
| **Tons frios e escuros** | Suspense, tecnologia, solidão |

---

## 10. Proporção e Resolução

### Proporção

| Proporção | Uso comum |
|---|---|
| **16:9** | Vídeos horizontais, YouTube, TV, computador |
| **9:16** | Vídeos verticais para celular, *stories*, *reels* e vídeos curtos |
| **1:1** | Publicações quadradas em redes sociais |
| **4:5** | Publicações verticais leves em redes sociais |
| **21:9** | Aparência de cinema, cenas panorâmicas |

### Resolução

| Nome | Resolução aproximada |
|---|---|
| **720p (HD)** | 1280 × 720 |
| **1080p (Full HD)** | 1920 × 1080 |
| **4K (UHD)** | 3840 × 2160 |

> As opções disponíveis dependem da ferramenta e do plano de uso. Escolha a proporção antes de gerar, pois ela influencia a composição.

---

## 11. Física e Interação

**Conceito:** os modelos avançados tentam imitar leis físicas reais, embora ainda possam falhar em detalhes complexos. Descrever o resultado esperado ajuda.

| Fenômeno | O que descrever | Exemplo |
|---|---|---|
| **Gravidade e queda** | Como objetos caem e quicam | Uma bola caindo e quicando no chão |
| **Colisões** | Impacto entre objetos | Duas bolas se chocando |
| **Líquidos** | Respingos, ondas, fluxo | Água ondulando ao toque, chá sendo servido |
| **Tecidos** | Dobras e movimento | Vestido balançando ao vento |
| **Cabelo e pelos** | Movimento sob vento ou ação | Cabelo flutuando em câmera lenta |
| **Fumaça, fogo e poeira** | Dispersão e turbulência | Fumaça subindo e se dissipando |
| **Reflexos e sombras** | Coerência com a luz e o movimento | Reflexo do neon em uma poça enquanto alguém passa |

Pontos em que os modelos ainda costumam errar:

| Ponto fraco | Exemplo |
|---|---|
| **Causa e efeito** | Um objeto que se quebra sem que algo o tenha atingido |
| **Permanência de objetos** | Um item que some ou aparece sem motivo |
| **Quantidades** | Mãos com dedos a mais, número de objetos que muda |
| **Interações complexas** | Mãos manipulando objetos pequenos |

---

## 12. Consistência de Personagens e Cenários

**Conceito:** manter o mesmo personagem, roupa e cenário ao longo de um clipe (ou de vários clipes) é um dos maiores desafios do vídeo por IA.

| Técnica | Como ajuda |
|---|---|
| **Imagem de primeiro quadro** | Ancora a aparência do personagem e do cenário |
| **Descrição fixa** | Repetir sempre as mesmas palavras para descrever o personagem |
| **Clipes curtos** | Menos tempo para o modelo "esquecer" detalhes |
| **Imagens de referência** | Algumas ferramentas aceitam imagens do personagem ou do estilo |
| **Seed fixa** | Em ferramentas que permitem, ajuda a repetir resultados |
| **Edição final** | Unir vários clipes curtos em um editor de vídeo |

---

## 13. Controles e Parâmetros

Os nomes e a disponibilidade variam de ferramenta para ferramenta.

| Controle | O que faz |
|---|---|
| **Duração** | Define o tamanho do clipe |
| **Proporção e resolução** | Definem o formato e a qualidade da imagem |
| **Intensidade de movimento** | Controla o quanto a cena se mexe (do sutil ao intenso) |
| **Controle de câmera** | Painel ou parâmetros para escolher tipo, direção e velocidade do movimento |
| **Primeiro e último quadro** | Fixam o início e o fim do clipe |
| **Imagem ou vídeo de referência** | Guia aparência, estilo ou movimento |
| **Prompt negativo** | Lista o que não deve aparecer |
| **Seed** | Número que ajuda a repetir um resultado |
| **Variações** | Gera alternativas do mesmo prompt |
| **Repetição em *loop*** | Tenta fazer o final se conectar ao início |

---

## 14. Problemas Comuns

| Problema | Aparência | O que tentar |
|---|---|---|
| **Tremulação** (*flickering*) | Brilho, cor ou detalhes piscando entre quadros | Clipes mais curtos, menos detalhes, movimento mais sutil |
| **Deformação** (*morphing*) | Rostos, objetos ou mãos que mudam de forma | Descrever menos ações, usar imagem de primeiro quadro |
| **Efeito fantasma** | Rastros e sobreposições em movimentos rápidos | Reduzir a velocidade do movimento |
| **Mudança de identidade** | O personagem muda de aparência | Descrição fixa e imagem de referência |
| **Movimento artificial** | Passos que "deslizam", gestos estranhos | Pedir movimentos mais simples e lentos |
| **Física errada** | Objetos que flutuam, atravessam ou somem | Descrever o resultado físico esperado, simplificar a cena |
| **Texto ilegível** | Letras trocadas ou borradas | Evitar texto na cena; acrescentar na edição |
| **Câmera instável** | Tremor ou movimento aleatório | Pedir "câmera estável" ou especificar o movimento |

---

## 15. Cuidados e Governança

Vídeos sintéticos são mais convincentes e mais fáceis de usar para enganar do que imagens. Valem os mesmos pilares do guia de [Governança de IA](../governanca-de-ia/README.md):

| Cuidado | Por quê |
|---|---|
| **Não reproduzir pessoas reais sem consentimento** | Risco de *deepfakes* e de enganar quem assiste |
| **Respeitar direitos autorais** | Evitar personagens, marcas e estilos protegidos |
| **Identificar conteúdo sintético** | Avisar que o vídeo foi gerado por IA, quando houver chance de confusão |
| **Respeitar as regras da plataforma** | Os *guardrails* bloqueiam violência, conteúdo adulto e figuras públicas |

---

## 16. Montando um Prompt Completo

Ordem sugerida: **sujeito e ação → contexto → câmera → enquadramento e lente → estilo → luz e cor → ritmo → formato**.

| Camada | Escolha |
|---|---|
| **Sujeito e ação** | Uma mulher de jaqueta laranja caminha lentamente em direção à câmera |
| **Contexto** | Rua de uma cidade futurista, à noite, chuva fina |
| **Câmera** | Dolly in lento, na altura dos olhos |
| **Enquadramento e lente** | Plano médio, lente de retrato com fundo desfocado |
| **Estilo** | Cinematográfico, 24 FPS |
| **Luz e cor** | Neon rosa e azul refletido no asfalto molhado, gradação azul-esverdeada e laranja |
| **Ritmo** | Lento e contemplativo |
| **Formato** | 16:9, 5 segundos |

Prompt resultante:

> Uma mulher de jaqueta laranja caminha lentamente em direção à câmera em uma rua de cidade futurista, à noite, com chuva fina. Dolly in lento na altura dos olhos, plano médio, lente de retrato com fundo desfocado. Estilo cinematográfico, 24 FPS, neon rosa e azul refletido no asfalto molhado, gradação azul-esverdeada e laranja. Ritmo lento e contemplativo. Formato 16:9, 5 segundos.

Checklist antes de gerar:

| Item | Verificação |
|---|---|
| Ação clara | Há um verbo principal e uma ação por clipe? |
| Câmera | O movimento foi descrito (tipo, direção e velocidade)? |
| Duração | O clipe é curto o suficiente para manter a coerência? |
| Formato | Proporção e resolução foram escolhidas? |
| Consistência | O personagem tem descrição fixa ou imagem de referência? |
| Conflitos | Há pedidos contraditórios (por exemplo, "câmera estática" e "dolly in")? |
| Cuidados | Há pessoas reais, marcas ou personagens protegidos na cena? |