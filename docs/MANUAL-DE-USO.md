# Manual de Uso — AETHER-AI

## Finalidade

O AETHER-AI ajuda você a executar tarefas repetitivas com IA usando apenas os agentes necessários, evitando retrabalho e consumo desnecessário de tokens.

## Como usar no Claude ou ChatGPT

1. Abra uma conversa nova.
2. Anexe ou disponibilize o arquivo `agents/01-diretor-ia.md`.
3. Envie sua solicitação no formato:

```text
Use o Diretor IA para conduzir esta tarefa.
Objetivo: [descreva o resultado desejado]
Contexto essencial: [somente informações indispensáveis]
Formato da entrega: [mensagem, artigo, plano, agente, documento etc.]
```

4. O Diretor deverá indicar se consegue resolver sozinho ou quais agentes adicionais são necessários.
5. Carregue somente os arquivos indicados.
6. Ao concluir, salve modelos reutilizáveis em `assets/`.

## Regra de economia de tokens

Nunca carregue todos os agentes ao mesmo tempo. Use o Diretor IA e acrescente somente os especialistas solicitados.

## Fluxos rápidos

### Tarefa simples

Diretor IA → entrega final.

### Criação de um agente

Diretor IA → Planejador → Engenheiro de Especificação → Compilador de Agentes → Revisor.

### Melhoria de um agente existente

Diretor IA → Revisor → Compilador de Agentes.

### Criação de conteúdo

Diretor IA → especialista de domínio escolhido → Revisor.

## Como pedir continuidade em outra conversa

Use:

```text
Projeto: AETHER-AI
Leia `STATUS.md` e os arquivos citados na seção Próxima tarefa.
Continue somente a etapa indicada, sem reconstruir o que já está pronto.
```

## Boas práticas

- Uma conversa deve ter um objetivo principal.
- Forneça apenas o contexto necessário.
- Reutilize templates e agentes existentes.
- Salve decisões importantes no projeto.
- Revise antes de transformar uma saída em modelo permanente.
