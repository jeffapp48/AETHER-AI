# Fluxo Oficial de Criação de Agentes — AETHER-AI

**Versão:** 1.0

## Objetivo

Definir o processo padrão utilizado pelo AETHER-AI para transformar uma necessidade do usuário em um agente hiperespecializado, documentado, testável e reutilizável.

## Regra central

O AETHER-AI deve criar somente os agentes necessários. Antes de criar um agente novo, deve verificar se já existe um agente, template ou asset que possa ser reutilizado ou adaptado.

## Fluxo resumido

```text
Solicitação do usuário
        ↓
Diretor IA
        ↓
Planejador
        ↓
Engenheiro de Especificação
        ↓
Compilador de Agentes
        ↓
Revisor
        ↓
Agente aprovado
        ↓
Registro na biblioteca
```

## Etapa 1 — Direção

Responsável: `agents/01-diretor-ia.md`

O Diretor IA deve:

1. identificar o problema real;
2. definir o resultado esperado;
3. avaliar a complexidade;
4. verificar possibilidade de reutilização;
5. decidir se a tarefa exige a criação de um agente;
6. acionar apenas os agentes centrais necessários.

### Saída

Uma decisão objetiva:

- resolver diretamente;
- adaptar um agente existente;
- criar um novo agente;
- solicitar apenas uma informação indispensável.

## Etapa 2 — Planejamento

Responsável: `agents/02-planejador.md`

O Planejador deve produzir um Plano Executivo contendo:

- objetivo;
- entregáveis;
- etapas;
- dependências;
- agentes necessários;
- assets reutilizáveis;
- riscos;
- critérios de conclusão.

O plano deve usar o menor fluxo capaz de entregar o resultado com qualidade.

## Etapa 3 — Especificação

Responsável: `agents/03-engenheiro-de-especificacao.md`

O Engenheiro de Especificação transforma o plano em um `AgentSpec` independente de plataforma.

O AgentSpec deve definir:

- identidade;
- missão;
- usuário;
- problema resolvido;
- objetivos;
- escopo;
- fora do escopo;
- entradas;
- saídas;
- conhecimentos;
- responsabilidades;
- fluxo de trabalho;
- regras;
- limitações;
- ferramentas;
- memória;
- tratamento de erros;
- formato das respostas;
- critérios de qualidade;
- testes.

### Regra

O AgentSpec não é o prompt final. Ele é a fonte de verdade do agente.

## Etapa 4 — Compilação

Responsável: `agents/04-compilador-de-agentes.md`

O Compilador converte o AgentSpec em um agente pronto para uso.

A entrega mínima deve conter:

1. Prompt Mestre em Markdown;
2. instruções de instalação;
3. instruções de uso;
4. mensagem de inicialização;
5. exemplos de entrada e saída;
6. limitações conhecidas;
7. versão para ChatGPT e Claude quando houver diferenças relevantes.

## Etapa 5 — Revisão

Responsável: `agents/05-revisor.md`

O Revisor verifica:

- fidelidade ao AgentSpec;
- ausência de requisitos inventados;
- especialização suficiente;
- clareza das entradas e saídas;
- coerência das regras;
- economia de tokens;
- segurança;
- tratamento de erros;
- qualidade dos testes;
- independência de plataforma.

### Resultado

- `APROVADO`;
- `APROVADO COM AJUSTES`;
- `REPROVADO`.

## Etapa 6 — Registro

Após aprovação:

1. salvar o agente em `agents/specialists/`;
2. salvar o AgentSpec em `assets/agent-specs/`;
3. registrar o agente no catálogo;
4. registrar os testes em `tests/agents/`;
5. atualizar `STATUS.md`;
6. versionar como `1.0.0`.

## Nomenclatura

### Agente

```text
agents/specialists/[dominio]/[nome-do-agente].md
```

### AgentSpec

```text
assets/agent-specs/[nome-do-agente].agentspec.md
```

### Testes

```text
tests/agents/[nome-do-agente].tests.md
```

## Critérios para criar um novo agente

Um agente novo somente deve ser criado quando:

- existe uma função recorrente e bem delimitada;
- a tarefa exige conhecimentos ou regras próprias;
- a reutilização economizará tempo ou tokens;
- um agente existente não atende com pequenas adaptações;
- entradas e saídas podem ser definidas claramente.

Não criar um agente quando:

- a tarefa é única e simples;
- um template resolve;
- o Diretor IA consegue executar diretamente;
- a especialidade é ampla demais;
- os requisitos ainda estão indefinidos.

## Definição de pronto

Um agente está pronto quando:

- possui AgentSpec completo;
- possui Prompt Mestre;
- possui instruções de uso;
- passou pelos testes mínimos;
- foi aprovado pelo Revisor;
- foi registrado no catálogo;
- pode ser carregado isoladamente sem depender da conversa original.
