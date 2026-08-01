# AETHER-AI

Plataforma prática para criar, organizar e reutilizar agentes de Inteligência Artificial com foco em economia de tempo, redução de retrabalho e baixo consumo de tokens.

## Objetivo

Ajudar o usuário a executar tarefas repetitivas usando um pequeno conjunto de agentes especializados, sem exigir conhecimento técnico avançado.

## Como funciona

1. O **Diretor IA** recebe a solicitação.
2. Ele decide se resolve diretamente ou se precisa de outros agentes.
3. O **Planejador** organiza tarefas maiores.
4. O **Engenheiro de Especificação** define agentes e soluções.
5. O **Compilador de Agentes** gera o prompt pronto para uso.
6. O **Revisor** valida a qualidade final.

## Início rápido

Leia:

- [`docs/MANUAL-DE-USO.md`](docs/MANUAL-DE-USO.md)
- [`agents/01-diretor-ia.md`](agents/01-diretor-ia.md)

Depois, no Claude ou ChatGPT, envie:

```text
Use o Diretor IA para conduzir esta tarefa.
Objetivo: [resultado desejado]
Contexto essencial: [informações indispensáveis]
Formato da entrega: [formato esperado]
```

## Estrutura

```text
AETHER-AI/
├── agents/       # Agentes centrais
├── assets/       # Materiais reutilizáveis
├── docs/         # Manuais
├── projects/     # Projetos em andamento
├── templates/    # Modelos prontos
├── README.md
└── STATUS.md
```

## Regra principal

Nunca carregue todos os agentes ao mesmo tempo. Comece pelo Diretor IA e acrescente somente os arquivos que ele indicar.

## Status

Versão inicial funcional em desenvolvimento. Consulte [`STATUS.md`](STATUS.md).
