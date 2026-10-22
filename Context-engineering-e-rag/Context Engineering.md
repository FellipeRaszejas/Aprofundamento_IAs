# Engenharia de Contexto

A engenharia de contexto é a especialização da engenharia de prompt. Ela consiste na construção estratégica e na otimização de todo o ambiente de dados (o **contexto**) fornecido a um LLM.

## Sumário

1. [Funcionamento](#1-funcionamento)
2. [Objetivo final](#2-objetivo-final)

## 1. Funcionamento

Ao enviar um pedido a um LLM, a resposta do modelo depende da informação fornecida. Pense em um funcionário novo: para responder bem, ele precisa das regras da empresa, de um exemplo de relatório pronto, do histórico do cliente e das ferramentas do sistema. Com o LLM é igual: além do que aprendeu no treinamento, ele só conta com o que está no contexto.

A engenharia de contexto organiza essa informação em quatro componentes:

| Componente | O que contém |
|---|---|
| **Instruções ao sistema** (*System Prompts*) | Regras de comportamento, tom de voz (se for usar), persona e restrições de segurança |
| **Exemplos de saída** (*few-shot prompting*) | Exemplo prático do formato exato da resposta desejada |
| **Dados relevantes** | Informações específicas sobre o usuário, histórico da conversa ou documentos externos |
| **Ferramentas disponíveis** | Lista de funções ou APIs que o modelo pode utilizar para resolver uma tarefa |

## 2. Objetivo final

Garantir que o LLM tenha exatamente a informação necessária para dar a resposta de que o usuário precisa, evitando respostas genéricas ou incorretas.