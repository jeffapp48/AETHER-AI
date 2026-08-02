# Contratos entre Agentes — AETHER-AI

**Versão:** 1.0

## Objetivo

Definir como os agentes centrais trocam informações sem reler toda a conversa, reduzindo consumo de tokens, perda de contexto e retrabalho.

## Regra principal

Cada agente recebe apenas o artefato necessário para sua função e entrega um novo artefato estruturado ao próximo agente.

```text
Pedido do usuário
  → Briefing Essencial
  → Plano Executivo
  → Especificação de Agente
  → Pacote do Agente
  → Relatório de Revisão
```

## Contrato 01 — Usuário para Diretor IA

### Entrada

`Briefing Essencial`

Campos mínimos:

- resultado desejado;
- quem utilizará o agente;
- tarefa principal;
- contexto indispensável;
- plataforma de destino, quando conhecida;
- restrições relevantes;
- formato esperado.

### Regra

Quando os dados forem suficientes, o Diretor não deve fazer novas perguntas. Quando faltar algo decisivo, deve fazer no máximo três perguntas objetivas.

### Saída

Uma destas decisões:

- resolver diretamente;
- reutilizar um agente existente;
- melhorar um agente existente;
- iniciar criação de novo agente.

Quando iniciar criação, produzir um `Resumo de Direção` para o Planejador.

## Contrato 02 — Diretor IA para Planejador

### Entrada

`Resumo de Direção`

Campos obrigatórios:

- objetivo real;
- resultado final observável;
- contexto essencial;
- restrições;
- assets conhecidos;
- decisão de criar, adaptar ou reutilizar.

### Saída

`Plano Executivo`, conforme `templates/PLANO-EXECUTIVO-TEMPLATE.md`.

### Garantias

- não executar a solução;
- não escrever o prompt final;
- selecionar o menor fluxo possível;
- declarar agentes dispensados quando isso evitar ambiguidade.

## Contrato 03 — Planejador para Engenheiro de Especificação

### Entrada

- `Plano Executivo` aprovado;
- requisitos confirmados;
- referências de assets autorizados.

### Saída

`Especificação de Agente`, conforme `templates/AGENT-SPEC-TEMPLATE.md`.

### Garantias

- independência de plataforma;
- nenhuma função inventada;
- entradas, saídas e limites verificáveis;
- lacunas decisivas marcadas como `PENDENTE`.

## Contrato 04 — Engenheiro de Especificação para Compilador

### Entrada

- `Especificação de Agente` aprovada;
- plataforma de destino;
- assets permitidos.

### Saída

`Pacote do Agente`, contendo:

1. Prompt Mestre;
2. instruções de instalação;
3. primeira mensagem de uso;
4. exemplos essenciais;
5. testes prontos para execução;
6. metadados de catálogo.

### Garantias

- o prompt não altera a especificação;
- o comportamento permanece equivalente entre plataformas;
- o conteúdo é econômico e sem repetições desnecessárias.

## Contrato 05 — Compilador para Revisor

### Entrada

- briefing ou resumo aprovado;
- especificação;
- pacote compilado;
- testes mínimos.

### Saída

`Relatório de Revisão`, conforme `templates/RELATORIO-REVISAO-TEMPLATE.md`.

### Vereditos

- `APROVADO`;
- `APROVADO_COM_AJUSTES`;
- `REPROVADO`.

### Garantias

- cada problema deve indicar evidência e correção;
- preferências estéticas não podem ser tratadas como erros críticos;
- a aprovação exige correspondência entre pedido, especificação e prompt.

## Regras de contexto

1. Nenhum agente recebe automaticamente a conversa completa.
2. O contexto deve ser resumido no artefato anterior.
3. Arquivos grandes só devem ser carregados quando forem fonte direta da tarefa.
4. Um agente não deve repetir o trabalho do anterior.
5. Se um artefato estiver incompleto, deve ser devolvido ao agente responsável, e não reconstruído silenciosamente.
6. Cada artefato deve registrar versão, data e status.

## Convenção de status

- `RASCUNHO`: ainda pode conter lacunas.
- `EM_REVISAO`: pronto para validação.
- `APROVADO`: autorizado para a próxima etapa.
- `SUBSTITUIDO`: mantido apenas para histórico.

## Critério de sucesso

O fluxo estará correto quando cada agente conseguir cumprir sua função lendo apenas seu contrato, o artefato de entrada e os assets explicitamente referenciados.