# miniguia-estudos-notebooklm: NotebookLM projeto de estudos

Este repositório documenta o processo de curadoria, extração de conhecimento e engenharia de prompts utilizando o **NotebookLM** da Google.

---

## 1. Contexto e Objetivos

O * **Assunto Escolhido** foi a linguagem de programação Go (Golang) e o **Objetivo de Estudo** é dominar os fundamentos da linguagem.

---

## 2. Curadoria de Fontes

Para alimentar a base de conhecimento do NotebookLM, foram selecionadas **4 fontes abertas de texto**, incluindo textos e documentação oficial tutorializada:

1. [Tutorials - The Go Programming Language](https://go.dev/doc/tutorial/)
2. [The Golang Handbook – A Beginner's Guide to Learning Go](https://www.freecodecamp.org/news/learn-golang-handbook/)
3. [O que é e como começar com Go (Golang)?](https://www.treinaweb.com.br/blog/o-que-e-e-como-comecar-com-golang)
4. [Golang](https://www.dio.me/technologies/golang)
5. [Como começar em Go (Golang): do zero ao seu primeiro programa](https://www.rocketseat.com.br/blog/artigos/post/golang-primeiros-passos)

---

## 3. Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Documentação do processo iterativo de perguntas, refinamentos e lições aprendidas ao extrair o melhor conhecimento da IA.

---

### Variações de Prompts e Respostas Obtidas

#### **Tentativa 1 (Prompt com Contexto, Restrições e Tarefas Complexas):**
> **Prompt:** *"Com base nas fontes, crie um quiz de 10 perguntas de múltipla escolha sobre concorrência em Go. Inclua o gabarito no final. As respostas do Quiz devem vir acompanhadas de explicações."*

> **Resultado:** A IA entregou o que foi pedido. No entanto, a formatação para um Quiz deixou a desejar.

#### **Tentativa 2 (Prompt Refinado com Formatação de Saída):**
Para tentar fazer a IA agrupar as alternativas não como a) X b) Y c) Z na mesma linha), tentei iterativamente um segundo prompt pedindo quebra de linha por alternativa para melhor legibilidade visual. Para isso usei a técnica de Output Formatting.

> **Prompt:** *"Com base nas fontes, crie um quiz de 10 perguntas de múltipla escolha sobre concorrência em Go. Inclua o gabarito no final. As respostas do Quiz devem vir acompanhadas de explicações. Estruture as respostas de múltipla escolha cada uma em sua própria linha.""*

> **Resultado:** Não funcionou, a IA entregou o mesmo resultado de formatação, apesar de ter feito modificações no conteúdo, como por exemplo a ordem de algumas perguntas ou repostas.

#### **Tentativa 3 (Prompt Refinado com Correção por Feedback e Restrição Negativa):**
Tentei novamente, agora usando "Correção por Feedback" e "Restrição Negativa", apontando explicitamente para a IA onde ela errou na resposta anterior, ou seja, também incluindo Contexto.

> **Prompt:** *"Você criou um quiz de 10 perguntas de múltipla escolha sobre concorrência em Go que pedi. Também incluiu o gabarito no final com respostas e explicações. Mas não estruturou as respostas de múltipla escolha cada uma em sua própria linha. Repita o processo anterior, mas agora separando as múltiplas escolhas de cada pergunta do Quiz por linhas."*

> **Resultado:** Também não funcionou, a IA continuou entregando o mesmo resultado de formatação.

#### **Tentativa 4 (Prompt Refinado com Few-Shot Prompting):**
Voltei ao prompt 2, e tentei adicionar exemplo de formatação.

> **Prompt:** *"Com base nas fontes, crie um quiz de 10 perguntas de múltipla escolha sobre concorrência em Go. Inclua o gabarito no final. As respostas do Quiz devem vir acompanhadas de explicações. Estruture as respostas de múltipla escolha cada uma em sua própria linha. Por exemplo:
> "Quiz: Concorrência em Go (Golang) \
> Qual palavra-chave é utilizada para iniciar uma goroutine em Go? \
> a) thread \
> b) run\
> c) go\
> d) parallel"*

> **Resultado:** Mais uma vez o resultado foi repetido. Provavelmente seja uma limitação do NotebookLM, já que no Gemini, quando acessado do Browser, esse tipo de refinamento de prompt costuma funcionar.

---

## 4. Miniguia de Estudo (Entrega Final)

Este miniguia consolida as lições aprendidas sobre Engenharia de Prompts durante a elaboração e testes práticos do NotebookLM

---

### Resumo Estruturado do Assunto

#### 1. Fundamentos e Contexto
* **Uso de Fontes Confiáveis:** A eficácia do prompt depende da qualidade das fontes escolhidas e carregadas no NotebookLM.
* **Redução de Alucinações:** Restringir explicitamente a resposta ao contexto fornecido (*"Com base nas fontes..."*) evita que a IA busque informações externas ou invente dados.

#### 2. Estruturação de Tarefas e Formatação
* **Clareza de Requisitos:** Delimitar regras claras (quantidade de itens, estilo de pergunta, presença de gabarito e explicações).
* **Desafios de Layout (com Formatação de Saída):** Instruções puramente textuais de formatação nem sempre alteram o comportamento visual do renderizador do NotebookLM, exigindo testes iterativos.

#### 3. Iteração e Limitações do Modelo
* **Engenharia Iterativa:** O refinamento exige testar variações de técnicas de Engenharia de Prompt.
* **Comportamento das Interfaces:** Uma mesma técnica (como o *Few-Shot*) pode responder de forma diferente dependendo da interface/ferramenta (ex: NotebookLM vs. Gemini no navegador).

---

### Glossário de Conceitos Fundamentais

| Conceito | Descrição |
| :--- | :--- |
| **Contexto** | Técnica de restringir a geração da IA estritamente aos documentos de contexto fornecidos, garantindo precisão. |
| **Restrições** | Definição clara de regras e limites para a resposta (ex: número de questões, escopo do tema, formato do gabarito). |
| **Formatação de Saída** | Instruções específicas para controlar o layout visual da resposta (ex: quebras de linha, tabelas, JSON). |
| **Feedback** | Técnica de refinamento onde se aponta explicitamente para a IA o erro cometido na tentativa anterior para que ela corrija. |
| **Few-Shot Prompting** | Prática de fornecer um ou mais exemplos visuais concretos do formato desejado diretamente no corpo do prompt. |

---

### Prompts Reutilizáveis para Revisões Futuras

Conjunto dos prompts desenvolvidos, testados e refinados durante a experiência para criação e formatação dos quizzes:

#### 1. Prompt Base (Prompt com Contexto, Restrições e Tarefas Complexas)
> *"Com base nas fontes, crie um quiz de 10 perguntas de múltipla escolha sobre [TEMA]. Inclua o gabarito no final. As respostas do Quiz devem vir acompanhadas de explicações."*

#### 2. Prompt com com Formatação de Saída
> *"Com base nas fontes, crie um quiz de 10 perguntas de múltipla escolha sobre [TEMA]. Inclua o gabarito no final. As respostas do Quiz devem vir acompanhadas de explicações. Estruture as respostas de múltipla escolha cada uma em sua própria linha."*

#### 3. Prompt Refinado com Correção por Feedback e Restrição Negativa
> *"Você criou o quiz sobre [TEMA] que pedi e incluiu o gabarito com explicações. Mas não estruturou as respostas de múltipla escolha cada uma em sua própria linha. Repita o processo anterior, mas agora separando as múltiplas escolhas de cada pergunta por linhas."*

#### 4. Prompt com Exemplo Concreto (Few-Shot Prompting)
> *"Com base nas fontes, crie um quiz de 10 perguntas de múltipla escolha sobre [TEMA]. Inclua o gabarito no final. As respostas do Quiz devem vir acompanhadas de explicações. Estruture as respostas de múltipla escolha cada uma em sua própria linha. Por exemplo:
> "Quiz: [TEMA]\
> [PERGUNTA]?\
> a) [OPÇÃO 1]\
> b) [OPÇÃO 2]\
> c) [OPÇÃO 3]\
> d) [OPÇÃO 4]"*
