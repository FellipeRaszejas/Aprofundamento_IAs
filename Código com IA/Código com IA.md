# O Equilíbrio Crítico: Engenharia Sólida vs. IA

Este guia explica por que a IA não substitui a engenharia de software, como os modelos de código são avaliados (HumanEval, SWE-bench e LiveCodeBench) e qual é o fluxo seguro para delegar código a uma IA.

## Sumário

1. [O Equilíbrio Crítico: Engenharia Sólida vs. IA](#1-o-equilíbrio-crítico-engenharia-sólida-vs-ia)
2. [Como os Modelos de Código São Avaliados (Benchmarks)](#2-como-os-modelos-de-código-são-avaliados-benchmarks)
3. [O Fluxo Seguro de Delegação](#3-o-fluxo-seguro-de-delegação)
   - [Passo 1: Especificação Clara](#passo-1-especificação-clara)
   - [Passo 2: Rede de Proteção (Testes)](#passo-2-rede-de-proteção-testes)
   - [Passo 3: Revisão Humana Crítica](#passo-3-revisão-humana-crítica)
4. [Resumo](#4-resumo)

---

## 1. O Equilíbrio Crítico: Engenharia Sólida vs. IA

**Conceito:** o maior erro de quem começa a usar IA para programar é achar que o modelo substitui a engenharia de software. A IA **acelera a escrita** (geração sintática), mas **não substitui a arquitetura** (projeto lógico).

**No dia a dia:** a IA é como uma furadeira elétrica: faz o furo muito mais rápido do que a mão. Mas ela não desenha a planta da casa. Sem a planta, a ferramenta só ajuda a errar mais depressa.

Sem bases sólidas de engenharia, a IA apenas ajuda a gerar um débito técnico estruturado muito mais rápido. Essas bases são:

| Base de engenharia | Para que serve |
|---|---|
| **Testes** | Provar que o código faz o que deveria |
| **Padrões de projeto** | Soluções conhecidas para problemas recorrentes de estrutura |
| **SOLID** | Princípios para manter o código organizado e fácil de mudar |
| **Revisão de código** | Segunda leitura crítica antes de aceitar a mudança |

| Quem faz | Papel |
|---|---|
| **IA** | Acelera a escrita (geração sintática) |
| **Pessoa engenheira** | Define a arquitetura (projeto lógico) e valida o resultado |

---

## 2. Como os Modelos de Código São Avaliados (Benchmarks)

**Conceito:** *benchmarks* são provas padronizadas que permitem comparar quão bem diferentes modelos escrevem código.

**No dia a dia:** são como provas de um curso. Uma tem exercícios de caderno, outra simula um estágio com problemas reais da empresa, e outra usa questões inéditas para ninguém conseguir decorar o gabarito.

| Benchmark | O que avalia | Diferencial |
|---|---|---|
| **HumanEval** (OpenAI) | A capacidade de resolver problemas isolados de programação a partir de descrições em texto (geração de funções corretas) | Problemas pequenos e independentes |
| **SWE-bench** | Se um agente de IA consegue resolver problemas reais do GitHub (corrigir *issues* e bugs complexos), lendo um repositório inteiro com vários arquivos e aplicando testes de regressão | Teste muito mais rigoroso e moderno, próximo do trabalho real |
| **LiveCodeBench** | Problemas novos e recentes | Evita que os modelos tenham "decorado" o benchmark durante o treinamento |

---

## 3. O Fluxo Seguro de Delegação

**Conceito:** o segredo do sucesso ao programar com IA resume-se a uma cadeia de três etapas.

| 📝 Especificação Clara | → | 🛡️ Rede de Proteção (Testes) | → | 🔍 Revisão Humana Crítica |
|:---:|:---:|:---:|:---:|:---:|

### Passo 1: Especificação Clara

Escrever o prompt com **contexto arquitetural** (Engenharia de Contexto aplicada a código). Quanto mais claro o pedido, menos a IA precisa adivinhar.

**No dia a dia:** é como o briefing para um profissional contratado. "Faça um site" gera surpresas; um briefing detalhado gera o resultado esperado.

### Passo 2: Rede de Proteção (Testes)

Ter **testes unitários e de integração** bem escritos **antes** de aceitar código gerado. Os testes dizem se o código novo faz o que deveria, independentemente de quem o escreveu.

```php
<?php
function calcularDesconto(float $preco, int $percentual): float
{
    return $preco - ($preco * $percentual / 100);
}
```

```php
<?php
use PHPUnit\Framework\TestCase;

final class DescontoTest extends TestCase
{
    public function testAplicaDezPorCento(): void
    {
        $this->assertSame(90.0, calcularDesconto(100.0, 10));
    }
}
```

- O primeiro bloco é uma função que poderia ter sido gerada pela IA.
- O segundo é o teste: ele afirma que 10% de desconto sobre 100 deve resultar em 90.
- Se a IA trocar a lógica por algo errado, o teste falha e o problema aparece antes de chegar à produção.

### Passo 3: Revisão Humana Crítica

Ler o *diff* do código gerado **linha por linha** para caçar:

| O que procurar | Exemplo |
|---|---|
| **Alucinações**: APIs inventadas que não existem nas bibliotecas | Chamar uma função que o PHP não possui |
| **Falhas lógicas sutis** | Condição que funciona nos casos comuns e falha nos limites |
| **Vulnerabilidades de injeção** | Valor do usuário colado direto em uma consulta SQL |

Exemplo de alucinação em PHP:

```php
<?php
$lista = [[1, 2], [3, [4]]];
$plano = array_flatten($lista); // função sugerida pela IA, mas que não existe no PHP
```

- **O que acontece:** o PHP encerra com erro de função indefinida (`Call to undefined function array_flatten()`).
- **Por que a revisão importa:** o código parece plausível e até "bem escrito", mas só quem lê com atenção percebe que a função foi inventada. No Laravel, o equivalente real é o `Arr::flatten()`.

---

## 4. Resumo

| Tema | Ideia central |
|---|---|
| **IA e engenharia** | A IA acelera a escrita, mas não substitui a arquitetura |
| **Sem bases sólidas** | Testes, padrões de projeto, SOLID e revisão evitam o débito técnico |
| **HumanEval** | Funções isoladas a partir de descrições |
| **SWE-bench** | Problemas reais do GitHub, com repositório inteiro e testes de regressão |
| **LiveCodeBench** | Problemas novos, para evitar que o modelo tenha decorado o benchmark |
| **Fluxo seguro** | Especificação clara → testes → revisão humana crítica |