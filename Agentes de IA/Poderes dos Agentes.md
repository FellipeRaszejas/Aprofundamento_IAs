# Function Calling: lista completa de ações

Function calling é o mecanismo que permite a um agente de IA agir no "mundo exterior". Esta lista reúne 130 exemplos do que um agente pode fazer, organizados por categoria.

> **Como funciona:** o modelo não executa a função sozinho. Ele devolve o nome da função e os argumentos, a aplicação executa e entrega o resultado de volta ao modelo. Por isso, cada agente só faz o que o desenvolvedor liberar, e ações sensíveis (apagar, pagar, enviar) merecem confirmação humana.

## Sumário

1. [Web e informação](#1-web-e-informação)
2. [Execução de código](#2-execução-de-código)
3. [Bancos de dados](#3-bancos-de-dados)
4. [Arquivos e documentos](#4-arquivos-e-documentos)
5. [Comunicação](#5-comunicação)
6. [Agenda e produtividade](#6-agenda-e-produtividade)
7. [Desenvolvimento e DevOps](#7-desenvolvimento-e-devops)
8. [Dados, cálculos e cotações](#8-dados-cálculos-e-cotações)
9. [Multimídia](#9-multimídia)
10. [Navegador e computador](#10-navegador-e-computador)
11. [Negócios e comércio](#11-negócios-e-comércio)
12. [Utilidades do sistema](#12-utilidades-do-sistema)
13. [Memória e conhecimento](#13-memória-e-conhecimento)

## 1. Web e informação

1. Pesquisar na web por palavras-chave
2. Abrir e ler o conteúdo de uma página
3. Extrair dados de páginas HTML (web scraping)
4. Consultar APIs públicas
5. Ler feeds RSS
6. Buscar notícias recentes
7. Consultar a Wikipédia e enciclopédias
8. Pesquisar artigos científicos
9. Traduzir o conteúdo de uma página
10. Verificar se um site está no ar

## 2. Execução de código

11. Executar código Python
12. Executar código PHP
13. Executar código Java
14. Executar código JavaScript
15. Rodar comandos de terminal (shell)
16. Executar testes automatizados
17. Instalar dependências em um ambiente isolado (sandbox)
18. Compilar projetos
19. Rodar linters e formatadores de código
20. Ler logs de erro e depurar

## 3. Bancos de dados

21. Consultar dados com SQL
22. Inserir registros
23. Atualizar registros
24. Excluir registros
25. Criar e alterar tabelas
26. Executar migrations
27. Consultar bancos NoSQL (como MongoDB)
28. Buscar blocos de texto em banco vetorial (RAG)
29. Exportar dados e gerar backups
30. Analisar o plano de execução de uma consulta

## 4. Arquivos e documentos

31. Ler arquivos de texto
32. Criar e editar arquivos
33. Listar pastas e diretórios
34. Mover, copiar e renomear arquivos
35. Apagar arquivos
36. Ler e extrair texto de PDFs
37. Gerar PDFs
38. Criar e ler documentos Word
39. Criar e ler planilhas Excel
40. Ler e converter CSV e JSON
41. Compactar e descompactar arquivos ZIP
42. Extrair texto de imagens (OCR)

## 5. Comunicação

43. Enviar e-mails
44. Ler a caixa de entrada
45. Responder e-mails
46. Enviar mensagens no Slack ou Teams
47. Enviar SMS
48. Enviar mensagens por WhatsApp (via API)
49. Fazer ligações com voz sintetizada
50. Publicar em redes sociais
51. Enviar notificações push
52. Comentar em issues e tickets de suporte

## 6. Agenda e produtividade

53. Criar e consultar eventos de calendário
54. Verificar disponibilidade e marcar reuniões
55. Criar tarefas e lembretes
56. Atualizar cartões no Trello ou Jira
57. Criar e editar páginas no Notion
58. Atualizar planilhas do Google
59. Gerenciar contatos
60. Definir alarmes e temporizadores
61. Resumir reuniões a partir de transcrições
62. Preencher formulários

## 7. Desenvolvimento e DevOps

63. Clonar repositórios Git
64. Criar branches
65. Fazer commits
66. Abrir pull requests
67. Comentar em revisões de código
68. Abrir e fechar issues
69. Disparar pipelines de CI/CD
70. Fazer deploy de aplicações
71. Consultar logs de servidores
72. Reiniciar serviços
73. Monitorar métricas (CPU, memória, disco)
74. Gerenciar containers Docker

## 8. Dados, cálculos e cotações

75. Calcular estatísticas
76. Gerar gráficos
77. Limpar e transformar dados (por exemplo, com pandas)
78. Treinar ou executar modelos de machine learning
79. Consultar cotações de ações
80. Converter moedas
81. Converter unidades de medida
82. Resolver cálculos matemáticos (calculadora)
83. Consultar a previsão do tempo
84. Converter endereços em coordenadas (geocodificação)

## 9. Multimídia

85. Gerar imagens
86. Analisar o conteúdo de imagens
87. Transcrever áudio em texto
88. Converter texto em fala (TTS)
89. Gerar ou editar vídeos
90. Extrair quadros de vídeos
91. Redimensionar e converter imagens
92. Gerar QR codes
93. Ler QR codes
94. Gerar legendas para vídeos

## 10. Navegador e computador

95. Abrir páginas em um navegador
96. Clicar em botões e links
97. Preencher campos de formulários
98. Fazer login em sites (com credenciais fornecidas)
99. Capturar telas (screenshots)
100. Rolar páginas
101. Baixar arquivos
102. Controlar mouse e teclado
103. Abrir aplicativos
104. Ler o conteúdo da tela

## 11. Negócios e comércio

105. Consultar estoque
106. Criar pedidos
107. Emitir faturas e notas fiscais
108. Processar pagamentos
109. Consultar dados de clientes em um CRM
110. Cadastrar leads
111. Rastrear entregas
112. Calcular frete
113. Reservar voos e hotéis
114. Comparar preços

## 12. Utilidades do sistema

115. Consultar data e hora atuais
116. Gerar números aleatórios e identificadores (UUID)
117. Validar e-mails, CPF e CNPJ
118. Aplicar expressões regulares (regex) em textos
119. Criptografar e descriptografar dados
120. Consultar endereços por CEP
121. Chamar outro agente
122. Pedir confirmação ao usuário antes de uma ação sensível

## 13. Memória e conhecimento

123. Salvar preferências do usuário
124. Recuperar o histórico de conversas
125. Buscar em uma base de conhecimento
126. Atualizar informações já memorizadas
127. Resumir conversas longas
128. Gerar embeddings de textos
129. Indexar documentos
130. Apagar informações da memória