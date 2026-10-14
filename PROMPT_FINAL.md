# PROMPT_FINAL

Documento com o planejamento da automação, seguindo as 3 etapas do desafio da DIO.

## Passo 1 — Definir a automação desejada

Criar uma automação simples no n8n que recebe uma tarefa de exemplo, verifica a sua prioridade e a encaminha para a saída correspondente (urgente ou normal).

Público: pessoas que precisam organizar tarefas simples do dia a dia.

## Passo 2 — Contexto e regras

- Ferramentas utilizadas: **n8n**, **Docker** e **OpenCode**.
- Fluxo: **Manual Trigger → Set Example → IF**.
- Regras:
  - Se `prioridade` = `"alta"`, a tarefa segue pela saída **TRUE** (urgente).
  - Caso contrário, segue pela saída **FALSE** (normal).
  - Utilizar apenas **3 nodes**.
  - Não utilizar APIs externas.

## Passo 3 — Prompt final completo

> Crie, no meu n8n local rodando em Docker, um workflow chamado "DIO - Organizador Simples de Tarefas" com apenas 3 nodes:
>
> 1. **Manual Trigger** — para iniciar o fluxo manualmente.
> 2. **Set Example** — para criar uma tarefa de exemplo com `tarefa = "Revisar proposta"` e `prioridade = "alta"` (ambos como texto).
> 3. **IF** — para verificar se a prioridade é igual a `"alta"`, usando a operação **equals**.
>
> Conecte os nodes na ordem Manual Trigger → Set Example → IF. Se a prioridade for "alta", a tarefa deve seguir pela saída TRUE (urgente); caso contrário, pela saída FALSE (normal). Mantenha o workflow inativo, use apenas 3 nodes e não utilize APIs externas.
