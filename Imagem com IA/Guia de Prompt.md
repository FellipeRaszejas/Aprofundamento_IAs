# Guia de Prompt Visual

Este guia reúne, em forma de consulta, os elementos que podem ser descritos em um prompt de geração de imagem: tipos de geração, sujeito, contexto, estilos, iluminação, paletas de cores, proporções, enquadramento, lentes, atmosfera e controles. Ele complementa o [README principal](README.md).

## Sumário

1. [Anatomia de um Prompt Visual](#1-anatomia-de-um-prompt-visual)
2. [Tipos de Geração](#2-tipos-de-geração)
3. [Sujeito](#3-sujeito)
4. [Contexto e Cenário](#4-contexto-e-cenário)
5. [Estilo e Categorias Visuais](#5-estilo-e-categorias-visuais)
   - [Técnica e meio](#técnica-e-meio)
   - [Movimentos e períodos artísticos](#movimentos-e-períodos-artísticos)
   - [Estéticas e gêneros](#estéticas-e-gêneros)
   - [Observação sobre nomes de artistas](#observação-sobre-nomes-de-artistas)
6. [Iluminação](#6-iluminação)
7. [Paleta de Cores](#7-paleta-de-cores)
   - [Esquemas de harmonia](#esquemas-de-harmonia)
   - [Temperatura, saturação e valor](#temperatura-saturação-e-valor)
   - [Paletas temáticas](#paletas-temáticas)
8. [Proporção (Aspect Ratio)](#8-proporção-aspect-ratio)
9. [Enquadramento, Ângulo e Composição](#9-enquadramento-ângulo-e-composição)
10. [Lente e Câmera](#10-lente-e-câmera)
11. [Atmosfera, Materiais e Nível de Detalhe](#11-atmosfera-materiais-e-nível-de-detalhe)
12. [Controles e Parâmetros](#12-controles-e-parâmetros)
13. [Montando um Prompt Completo](#13-montando-um-prompt-completo)

---

## 1. Anatomia de um Prompt Visual

**Conceito:** um prompt visual é uma descrição organizada em camadas. Quanto mais camadas você especifica, menos a IA precisa adivinhar.

**No dia a dia:** é como passar instruções a um fotógrafo ou ilustrador. Dizer só "uma foto de uma mulher" deixa todas as decisões com ele; dizer quem, onde, com que luz, em que formato e em que estilo entrega o resultado que você imaginou.

| Camada | Pergunta que responde | Seção |
|---|---|---|
| **Sujeito** | Quem ou o que aparece? | [3](#3-sujeito) |
| **Contexto** | Onde, quando, em que clima? | [4](#4-contexto-e-cenário) |
| **Estilo** | Com que linguagem visual? | [5](#5-estilo-e-categorias-visuais) |
| **Iluminação** | Como a luz incide? | [6](#6-iluminação) |
| **Paleta de cores** | Quais cores dominam? | [7](#7-paleta-de-cores) |
| **Proporção** | Qual o formato da imagem? | [8](#8-proporção-aspect-ratio) |
| **Enquadramento e composição** | De onde e como a cena é vista? | [9](#9-enquadramento-ângulo-e-composição) |
| **Lente e câmera** | Que efeito fotográfico? | [10](#10-lente-e-câmera) |
| **Atmosfera, materiais e detalhe** | Que sensação e acabamento? | [11](#11-atmosfera-materiais-e-nível-de-detalhe) |
| **Controles** | O que evitar, o que fixar? | [12](#12-controles-e-parâmetros) |

> Nem toda camada é obrigatória. Comece com sujeito, contexto e estilo e vá acrescentando as demais conforme o resultado.

---

## 2. Tipos de Geração

Antes de escrever o prompt, vale saber o que você quer fazer. Cada tipo exige um tipo de entrada diferente.

| Tipo | O que faz | Entrada |
|---|---|---|
| **Texto para imagem** (*text-to-image*) | Cria uma imagem do zero | Só o texto |
| **Imagem para imagem** (*img2img*) | Gera uma variação a partir de uma imagem existente | Imagem + texto |
| **Inpainting** | Refaz só uma região marcada da imagem | Imagem + máscara + texto |
| **Outpainting** | Estende a imagem além das bordas originais | Imagem + texto |
| **Ampliação** (*upscaling*) | Aumenta a resolução e os detalhes | Imagem |
| **Transferência de estilo** | Aplica o estilo de uma imagem a outra | Duas imagens |
| **Geração controlada** | Segue uma estrutura (pose, bordas, profundidade) | Imagem de controle + texto (veja [ControlNet](#12-controles-e-parâmetros)) |

> Os nomes e a disponibilidade desses recursos variam de ferramenta para ferramenta.

---

## 3. Sujeito

**Conceito:** o sujeito é o centro da imagem. Descreva-o com o máximo de especificidade que a cena exigir.

| Categoria | Exemplos |
|---|---|
| **Pessoas** | Retrato, grupo, multidão, criança, idoso, profissional de uma área |
| **Animais** | Gato, cavalo, ave em voo, animal pré-histórico |
| **Personagens** | Herói, vilão, mascote original, robô, androide |
| **Criaturas fantásticas** | Dragão, fada, monstro, ser alienígena |
| **Objetos** | Relógio, xícara, sapato, produto sobre uma mesa |
| **Veículos** | Carro, nave espacial, barco, bicicleta |
| **Alimentos** | Prato gourmet, sobremesa, ingredientes soltos |
| **Paisagens** | Montanha, praia, floresta, deserto, cidade ao longe |
| **Arquitetura** | Casa, templo, arranha-céu, interior de um cômodo |

Atributos que tornam o sujeito mais preciso:

| Atributo | Exemplos |
|---|---|
| **Aparência** | Idade aproximada, cabelo, roupa, acessórios |
| **Expressão** | Sorrindo, séria, assustada, concentrada |
| **Pose e ação** | Correndo, sentada, olhando para trás, segurando um objeto |
| **Quantidade** | Um, três, um grupo pequeno |
| **Material e cor** | Armadura de bronze, vestido vermelho, madeira escura |

> Para sujeitos que existem de fato (marcas, personagens protegidos, pessoas reais), as plataformas costumam aplicar restrições. Prefira descrever personagens originais.

---

## 4. Contexto e Cenário

**Conceito:** o contexto situa o sujeito no mundo: onde, quando e em que condições.

| Elemento | Exemplos |
|---|---|
| **Local** | Floresta, rua movimentada, biblioteca, nave, laboratório, cozinha |
| **Ambiente** | Interior ou exterior; urbano, rural ou natural |
| **Época** | Pré-história, Idade Média, século XIX, anos 1980, futuro distante |
| **Hora do dia** | Amanhecer, meio-dia, fim de tarde, noite |
| **Estação** | Primavera, verão, outono, inverno |
| **Clima** | Ensolarado, nublado, chuva, neve, tempestade, neblina |
| **Fundo** | Desfocado, liso, detalhado, estúdio com fundo infinito |

---

## 5. Estilo e Categorias Visuais

**Conceito:** o estilo define a "linguagem" da imagem. É a seção em que entram categorias como 2D, 3D, cyberpunk, medieval e realismo.

### Técnica e meio

| Categoria | Variações |
|---|---|
| **2D** | Ilustração plana (*flat*), vetorial, cartum, anime e mangá, *pixel art*, *line art* (traço), quadrinhos |
| **3D** | Render 3D, *low poly*, isométrico, massinha (*clay*), *voxel*, personagem estilo animação 3D |
| **Fotografia** | Retrato, paisagem, documental, rua, produto, macro, aérea, analógica |
| **Pintura** | Óleo, aquarela, acrílico, guache, pintura digital |
| **Desenho** | Lápis, carvão, nanquim, caneta, giz pastel |
| **Artesanal** | Colagem, *papercraft* (dobradura e recorte de papel), bordado, vitral, mosaico |
| **Técnico** | Planta e *blueprint*, diagrama, ilustração científica, infográfico |

### Movimentos e períodos artísticos

| Movimento | Característica resumida |
|---|---|
| **Renascimento** | Proporção, perspectiva e realismo clássico |
| **Barroco** | Contraste forte entre luz e sombra, drama |
| **Impressionismo** | Pinceladas soltas, foco na luz e na cor |
| **Expressionismo** | Emoção intensa, formas e cores distorcidas |
| **Cubismo** | Objeto visto de vários ângulos ao mesmo tempo |
| **Surrealismo** | Cenas oníricas e combinações impossíveis |
| **Art Nouveau** | Linhas orgânicas e ornamentos inspirados na natureza |
| **Art Déco** | Geometria, simetria e luxo |
| **Bauhaus** | Formas simples, funcionais e geométricas |
| **Pop Art** | Cores chapadas, cultura de massa, quadrinhos |
| **Minimalismo** | Poucos elementos, muito espaço vazio |
| **Ukiyo-e** | Gravura japonesa tradicional, linhas definidas e cores planas |

### Estéticas e gêneros

| Estética | Característica resumida |
|---|---|
| **Realismo** | Fiel à aparência do mundo real |
| **Hiper-realismo / fotorrealismo** | Detalhe e textura próximos de uma fotografia |
| **Cyberpunk** | Futuro urbano, neon, tecnologia avançada e decadência social |
| **Steampunk** | Tecnologia a vapor, engrenagens, estética vitoriana |
| **Solarpunk** | Futuro otimista, sustentável, cheio de plantas e energia limpa |
| **Medieval** | Castelos, armaduras, vilas e cavaleiros |
| **Fantasia** | Magia, criaturas e mundos imaginários |
| **Ficção científica** | Espaço, naves, planetas e tecnologia futurista |
| **Retrofuturista** | O futuro como era imaginado no passado |
| **Vaporwave / synthwave** | Neon rosa e azul, estética dos anos 1980, grades e palmeiras |
| **Gótico / sombrio** | Atmosfera pesada, tons escuros, arquitetura imponente |
| **Noir** | Preto e branco, sombras marcadas, clima de filme policial |
| **Pós-apocalíptico** | Ruínas, natureza retomando a cidade |
| **Cottagecore** | Vida rural idealizada, flores, tons suaves |

### Observação sobre nomes de artistas

Pedir "no estilo de" um artista vivo é um dos pontos mais debatidos sobre direitos autorais (veja a [seção 4 do README](README.md#4-onde-isso-se-conecta-com-a-governança-e-os-agentes)). Uma alternativa mais segura e muitas vezes mais precisa é **descrever as características** do estilo: tipo de traço, textura, paleta e composição.

---

## 6. Iluminação

**Conceito:** a luz define o clima, o volume e o foco da imagem. É um dos elementos de maior impacto no resultado.

| Tipo | Descrição | Efeito |
|---|---|---|
| **Hora dourada** (*golden hour*) | Luz do sol baixo, logo após o nascer ou antes do pôr do sol | Quente, suave, alaranjada |
| **Hora azul** (*blue hour*) | Minutos antes do amanhecer ou depois do pôr do sol | Azulada, calma |
| **Sol do meio-dia** | Luz alta e direta | Sombras curtas e duras |
| **Dia nublado** | Luz difusa | Suave, sem sombras marcadas |
| **Luz de estúdio** | Luz controlada, com *softbox* | Limpa, profissional |
| **Luz Rembrandt** | Luz lateral que forma um triângulo de luz na bochecha | Retrato dramático e clássico |
| **Luz borboleta** (*butterfly*) | Luz frontal vinda de cima | Retrato glamouroso, sombra sob o nariz |
| **Contraluz e luz de contorno** (*rim light*) | Luz por trás do sujeito | Contorno brilhante, destaque do sujeito |
| **Silhueta** | Sujeito escuro contra fundo claro | Forma sem detalhes internos |
| **Neon** | Luzes coloridas artificiais | Urbano, noturno, futurista |
| **Luz de vela ou fogueira** | Luz quente e bruxuleante | Íntimo, aconchegante |
| **Luz volumétrica** | Raios de luz visíveis no ar (névoa, poeira) | Atmosfera épica ou mística |
| **Cinematográfica** | Luz dramática, com contraste e cor intencionais | Aparência de filme |
| **Low-key / high-key** | Predomínio de tons escuros (*low-key*) ou claros (*high-key*) | Sombrio e dramático ou leve e luminoso |

---

## 7. Paleta de Cores

**Conceito:** a paleta é o conjunto de cores que dominam a imagem. Ela pode ser pedida pelo **esquema de harmonia**, pela **temperatura/saturação/valor** ou por **nomes de cores**.

**No dia a dia:** é como escolher a decoração de uma sala. Você pode combinar tudo em tons parecidos (calmo), usar cores opostas (vibrante) ou limitar a poucas cores (elegante).

### Esquemas de harmonia

| Esquema | Como funciona | Efeito |
|---|---|---|
| **Monocromático** | Variações de uma única cor (claras e escuras) | Coeso, calmo |
| **Análogo** | Cores vizinhas no círculo cromático (azul, azul-esverdeado, verde) | Harmônico, suave |
| **Complementar** | Cores opostas (azul e laranja) | Contraste forte, vibrante |
| **Complementar dividido** | Uma cor e as duas vizinhas da sua oposta | Contraste com mais equilíbrio |
| **Triádico** | Três cores equidistantes (vermelho, amarelo, azul) | Vivo e equilibrado |
| **Tetrádico** | Quatro cores em dois pares complementares | Rico, exige cuidado para não poluir |
| **Preto e branco** | Sem cor, só luz e sombra | Clássico, dramático |
| **Sépia** | Tons de marrom | Aparência antiga |
| **Duotone** | Duas cores apenas | Gráfico, impactante |

### Temperatura, saturação e valor

| Propriedade | Opções | Efeito |
|---|---|---|
| **Temperatura** | Quente (vermelhos, laranjas, amarelos) ou fria (azuis, verdes, roxos) | Quente: acolhedor, energia. Frio: calma, distância |
| **Saturação** | Vibrante (cores intensas), pastel (suaves e claras), dessaturada (acinzentada) | Vibrante: energia. Pastel: delicadeza. Dessaturada: seriedade |
| **Valor (claro/escuro)** | Tons claros, médios ou escuros | Claro: leve. Escuro: dramático |
| **Contraste** | Alto ou baixo | Alto: forte e nítido. Baixo: suave e discreto |

### Paletas temáticas

| Paleta | Cores típicas |
|---|---|
| **Terrosa** | Marrom, ocre, terracota, verde-musgo |
| **Outonal** | Laranja, vermelho queimado, mostarda, marrom |
| **Oceânica** | Azul-petróleo, turquesa, areia, branco |
| **Neon** | Rosa, ciano, roxo e verde brilhantes sobre fundo escuro |
| **Vintage** | Cores desbotadas, amarelados, tons de creme |
| **Pastel** | Rosa-bebê, azul-claro, lilás, menta |
| **Metálica** | Dourado, prata, bronze, cobre |

> Você também pode citar cores pelo nome ("azul-petróleo", "vermelho-carmim", "verde-oliva") ou, em algumas ferramentas, pelo código hexadecimal (como `#1F4E79`). Dois ou três nomes de cor costumam funcionar melhor do que uma lista longa.

---

## 8. Proporção (Aspect Ratio)

**Conceito:** a proporção é a relação entre largura e altura da imagem. Ela define o formato do "quadro" e deve ser escolhida **antes** de gerar, pois influencia a composição.

**No dia a dia:** é como escolher o tamanho da moldura antes de pintar o quadro. Uma cena panorâmica não cabe bem em uma moldura quadrada.

| Proporção | Formato | Uso comum |
|---|---|---|
| **1:1** | Quadrado | Avatares, posts em redes sociais, ícones |
| **4:3** | Levemente retangular | Fotografia clássica, apresentações antigas |
| **3:2** | Retangular | Fotografia de câmeras profissionais |
| **16:9** | Widescreen | Vídeos, banners, telas de computador e TV |
| **21:9** | Panorâmico | Aparência de cinema, cenas amplas |
| **4:5** | Retrato leve | Publicações verticais em redes sociais |
| **3:4 e 2:3** | Retrato | Fotos verticais, pôsteres, capas |
| **9:16** | Vertical | Vídeos curtos, *stories*, papéis de parede de celular |

Como informar a proporção depende da ferramenta:

| Forma | Exemplo |
|---|---|
| **No texto do prompt** | "imagem em formato panorâmico 21:9" |
| **Parâmetro da ferramenta** | No Midjourney, `--ar 16:9` ao final do prompt |
| **Opção da interface** | Seletor de formato ou campos de largura e altura em pixels |

---

## 9. Enquadramento, Ângulo e Composição

**Conceito:** define de onde a cena é vista e como os elementos se distribuem dentro do quadro.

### Enquadramento (distância)

| Plano | O que mostra |
|---|---|
| **Plano geral / panorâmico** | O cenário inteiro; o sujeito é pequeno |
| **Plano aberto (corpo inteiro)** | O sujeito da cabeça aos pés, com ambiente |
| **Plano médio** | Do tronco para cima |
| **Close-up (primeiro plano)** | O rosto ou um objeto de perto |
| **Plano detalhe** | Uma parte específica (olho, mão, textura) |

### Ângulo de câmera

| Ângulo | Efeito |
|---|---|
| **Na altura dos olhos** | Neutro, natural |
| **Contra-plongée (de baixo para cima)** | O sujeito parece grande e imponente |
| **Plongée (de cima para baixo)** | O sujeito parece pequeno ou vulnerável |
| **Aéreo / drone** | Visão ampla de cima, em perspectiva |
| **Zenital (de cima, a 90°)** | Vista diretamente de cima, como em um mapa |
| **Ângulo holandês** | Câmera inclinada, sensação de tensão e desequilíbrio |
| **Primeira pessoa (POV)** | Cena vista pelos olhos do personagem |
| **Sobre o ombro** | Vista de trás de um personagem para outro |

### Composição

| Técnica | Como funciona |
|---|---|
| **Regra dos terços** | O sujeito fica em uma das linhas ou cruzamentos de uma grade 3x3 |
| **Centralizada / simétrica** | Sujeito no centro, equilíbrio dos dois lados |
| **Linhas guia** | Estradas, corredores ou rios que conduzem o olhar ao sujeito |
| **Moldura natural** | Portas, janelas ou galhos emoldurando o sujeito |
| **Espaço negativo** | Muito espaço vazio ao redor do sujeito |
| **Camadas de profundidade** | Primeiro plano, plano médio e fundo bem definidos |

---

## 10. Lente e Câmera

**Conceito:** termos fotográficos influenciam a aparência da imagem porque os modelos aprenderam com milhões de fotos acompanhadas de descrições. O efeito é uma **aproximação visual**, e não uma simulação física da câmera.

### Distância focal

| Lente | Distância focal aproximada | Efeito |
|---|---|---|
| **Olho de peixe** (*fisheye*) | 8 a 15 mm | Distorção circular extrema |
| **Ultra grande angular** | 14 a 24 mm | Cena muito ampla, perspectiva exagerada |
| **Grande angular** | 24 a 35 mm | Cena ampla, comum em paisagens e arquitetura |
| **Normal** | cerca de 50 mm | Aparência próxima à visão humana |
| **Retrato** | 85 a 135 mm | Rostos naturais, fundo suavemente desfocado |
| **Teleobjetiva** | 200 mm ou mais | Compressão de planos, sujeito distante em destaque |
| **Macro** | Lente de aproximação | Detalhes minúsculos em grande escala |
| **Tilt-shift** | Lente com inclinação | Efeito de cidade em miniatura |

### Abertura, movimento e filme

| Elemento | Opções | Efeito |
|---|---|---|
| **Abertura** | f/1.4 a f/2.8 (aberta) | Fundo bem desfocado, *bokeh*, sujeito isolado |
| | f/8 a f/16 (fechada) | Tudo nítido, do primeiro plano ao fundo |
| **Movimento** | Congelado, ou longa exposição (*motion blur*) | Ação parada ou rastros de luz e movimento |
| **Grão** | Alto ISO, grão de filme | Aparência analógica, mais crua |
| **Filme e câmera** | Polaroid, câmera descartável, filme analógico, preto e branco granulado | Aparência retrô, tons característicos |

---

## 11. Atmosfera, Materiais e Nível de Detalhe

### Atmosfera (humor)

| Categoria | Exemplos |
|---|---|
| **Emoção** | Sereno, alegre, nostálgico, melancólico, tenso, misterioso, épico, onírico |
| **Elementos atmosféricos** | Névoa, neblina, chuva, poeira no ar, fumaça, brilho, partículas flutuando |

### Materiais e texturas

| Tipo | Exemplos |
|---|---|
| **Naturais** | Madeira, pedra, areia, folhas, água, gelo |
| **Fabricados** | Metal polido, vidro, cerâmica, plástico, concreto |
| **Têxteis** | Seda, algodão, couro, veludo, tricô |
| **Acabamento** | Fosco, brilhante, desgastado, enferrujado, molhado, empoeirado |

### Nível de detalhe e qualidade

| Pedido | Efeito |
|---|---|
| **Altamente detalhado** | Mais texturas e elementos pequenos |
| **Minimalista / simples** | Poucos elementos, formas limpas |
| **Nítido / alta resolução** | Bordas e texturas bem definidas |
| **Aparência de acabamento profissional** | Imagem polida, no estilo de portfólio |

> Expressões de qualidade genéricas, como "obra-prima", têm efeito variável e dependem do modelo. Descrever o que você quer ver costuma render mais.

---

## 12. Controles e Parâmetros

**Conceito:** além do texto, as ferramentas oferecem controles que afinam o resultado. Os nomes e a disponibilidade variam de ferramenta para ferramenta.

| Controle | O que faz |
|---|---|
| **Prompt negativo** | Lista o que **não** deve aparecer (por exemplo, "borrado, texto, mãos extras"). No Midjourney, usa-se `--no`; no Stable Diffusion, há um campo próprio |
| **Imagem de referência** | Guia o resultado com uma imagem de exemplo (estilo, composição ou sujeito) |
| **Seed (semente)** | Número que fixa o ponto de partida do ruído; mesmo prompt e mesma *seed* tendem a gerar resultados parecidos |
| **Escala de fidelidade ao prompt** (CFG) | Define o quanto o modelo segue o texto à risca |
| **Passos** (*steps*) | Quantidade de etapas de *denoising* |
| **Variações** | Gera alternativas a partir de uma imagem já criada |
| **Inpainting e outpainting** | Edita uma região ou estende a imagem (veja a [seção 2](#2-tipos-de-geração)) |

Controles de estrutura (**ControlNet**) permitem guiar a imagem por um desenho de apoio:

| Tipo de controle | O que fixa |
|---|---|
| **Bordas** (*Canny*) | Contornos de uma imagem de referência |
| **Pose** (*OpenPose*) | Posição do corpo de uma figura humana |
| **Profundidade** (*depth*) | Distância dos elementos em relação à câmera |
| **Rabisco** (*scribble*) | Um esboço simples feito à mão |
| **Segmentação** | Regiões da imagem (céu, chão, objeto) |

---

## 13. Montando um Prompt Completo

Juntando as camadas, a ordem sugerida é: **sujeito → ação → contexto → estilo → iluminação → paleta → enquadramento → lente → atmosfera → proporção**.

| Camada | Escolha |
|---|---|
| **Sujeito e ação** | Um astronauta cavalgando um cavalo |
| **Contexto** | Na superfície da lua, com a Terra ao fundo |
| **Estilo** | Ilustração digital, estética de ficção científica |
| **Iluminação** | Luz de contorno, sol baixo |
| **Paleta** | Tons frios, azul e prata, com um toque de laranja |
| **Enquadramento** | Plano aberto, de baixo para cima |
| **Lente** | Grande angular |
| **Atmosfera** | Épica e silenciosa |
| **Proporção** | 16:9 |

Prompt resultante:

> Um astronauta cavalgando um cavalo na superfície da lua, com a Terra ao fundo, ilustração digital de ficção científica, luz de contorno e sol baixo, paleta de tons frios em azul e prata com um toque de laranja, plano aberto visto de baixo para cima, grande angular, atmosfera épica e silenciosa, formato 16:9

Checklist antes de gerar:

| Item | Verificação |
|---|---|
| Sujeito claro | Está descrito com atributos suficientes? |
| Contexto | Local, hora e clima estão definidos? |
| Estilo | Há uma linguagem visual escolhida? |
| Luz e cor | Iluminação e paleta foram citadas? |
| Formato | A proporção foi definida antes de gerar? |
| Conflitos | Há pedidos que se contradizem (por exemplo, "minimalista" e "altamente detalhado")? |
| Restrições | O que deve ser evitado foi informado? |

> Muitos modelos foram treinados principalmente com descrições em inglês. Se o resultado em português não sair como esperado, vale testar o mesmo prompt em inglês.