# DIO - Organizador Simples de Tarefas (n8n)

Projeto do desafio da DIO **"Planejando Automações com N8N Usando Apenas Bons Prompts"**.

## Objetivo

Criar uma automação simples no n8n que recebe uma tarefa de exemplo, verifica a sua prioridade e a encaminha para a saída correta: **urgente** (prioridade alta) ou **normal** (demais prioridades).

## Tecnologias utilizadas

- **n8n** — para montar e executar o fluxo.
- **Docker** — para rodar o n8n localmente.
- **OpenCode** — assistente usado para planejar e configurar a automação por meio de prompts.

## Explicação dos 3 nodes

1. **Manual Trigger** — inicia o fluxo manualmente, com um clique.
2. **Set Example** — cria a tarefa de exemplo, com os campos:
   - `tarefa` = `"Revisar proposta"`
   - `prioridade` = `"alta"`
3. **IF** — verifica se a prioridade é igual a `"alta"`:
   - Se for **alta** → saída **TRUE** (urgente).
   - Caso contrário → saída **FALSE** (normal).

## Como o fluxo funciona

Manual Trigger → Set Example → IF

O fluxo começa quando o Manual Trigger é acionado. Em seguida, o Set Example monta a tarefa de exemplo com a prioridade definida. Por último, o IF compara a prioridade: se for `"alta"`, o item segue pela saída TRUE (urgente); se for diferente, segue pela saída FALSE (normal).

## Imagem da execução

![Execução bem-sucedida](imagens/execucao-sucesso.png)

## Resultado do teste

Execução concluída com **sucesso**. O node Set Example gerou o item:

```json
{
  "tarefa": "Revisar proposta",
  "prioridade": "alta"
}
```

O node IF encaminhou **1 item para a saída TRUE** (prioridade alta / urgente) e **0 itens para a saída FALSE**. Ou seja, a classificação funcionou como esperado.
