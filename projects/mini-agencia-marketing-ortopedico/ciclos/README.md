# Ciclos da Mini Agência

Esta pasta armazena os conteúdos produzidos pela Mini Agência, separados por ciclo mensal.

## Estrutura padrão

Cada ciclo deve usar o formato `AAAA-MM` e conter:

- `CALENDARIO.md` — visão gerencial do ciclo, ordem, função editorial e status.
- `CONTEUDOS.md` — scripts completos prontos para gravação/publicação.
- `FONTES.md` — referências científicas e como sustentam cada conteúdo.
- `RESULTADOS.md` — métricas após publicação e decisões de Double Down.

## Status oficiais

Todo conteúdo deve usar apenas um dos status:

`Planejado → Aprovado → A gravar → Gravado → Publicado → Analisado`

Conteúdo bônus nunca é tratado como atraso.

## Comandos de uso

O usuário pode acionar a operação com linguagem natural. Exemplos oficiais:

- `Mini Agência, crie o próximo ciclo.`
- `Mini Agência, próximo conteúdo.`
- `Mini Agência, crie um conteúdo sobre [tema].`
- `Mini Agência, registre o Reel [número] como gravado.`
- `Mini Agência, registre o Reel [número] como publicado.`
- `Mini Agência, analise os resultados do ciclo.`

O Diretor IA deve interpretar variações equivalentes e encaminhar para este projeto sem exigir frase exata.

## Regra operacional

O GitHub é a memória permanente da operação. A conversa com a IA é a interface de trabalho. Sempre que o usuário pedir o próximo conteúdo, a IA deve consultar o ciclo ativo e entregar somente o item necessário, sem obrigar o usuário a navegar manualmente pelos arquivos.