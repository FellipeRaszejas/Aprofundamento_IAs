# RAG (Retrieval-Augmented Generation)

O RAG, ou **Geração Aumentada por Recuperação**, é uma técnica que busca informações em uma base de dados externa e as entrega ao LLM antes de ele responder.

## Sumário

1. [Limitações dos LLMs](#1-limitações-dos-llms)
2. [Funcionamento do RAG](#2-funcionamento-do-rag)

## 1. Limitações dos LLMs

O LLM possui três limitações principais, e o RAG surge para resolvê-las:

| Limitação | Descrição |
|---|---|
| **Dados desatualizados** | O modelo é limitado à sua data de treinamento |
| **Falta de dados privados** | Os documentos de uma empresa são privados, então um software pode ficar sem acesso a informações importantes |
| **Alucinações** | Sem uma base de dados boa (ou uma instrução precisa), o modelo pode produzir uma resposta que soa verdadeira, mas está incorreta |

Uma analogia cotidiana é a prova com consulta: em vez de decorar todo o conteúdo, o aluno consulta o livro certo na hora de responder. O RAG entrega esse livro ao LLM.

## 2. Funcionamento do RAG

O RAG funciona em três etapas:

| 1. Ingestão (preparação) | | 2. Recuperação | | 3. Geração |
|:---:|:---:|:---:|:---:|:---:|
| 📄 | → | 🔎 | → | 🧠 |
| Os documentos (PDFs, sites etc.) são divididos em pequenos blocos de texto (**chunks**).<br><br>Cada bloco é convertido em um vetor (**embedding**) e armazenado em um **banco de dados vetorial** (como Pinecone ou ChromaDB). | | A pergunta do usuário também é convertida em um vetor.<br><br>O sistema faz uma **busca semântica** no banco vetorial para encontrar os blocos de texto mais relevantes para o assunto perguntado. | | O sistema junta a pergunta com os trechos encontrados e envia ao LLM, com instruções mais detalhadas sobre o texto que deve ser produzido.<br><br>O LLM gera a resposta com base nesses trechos. |