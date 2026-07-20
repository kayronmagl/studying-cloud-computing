AWS Step Functions é o serviço da AWS para coordenar workflows usando máquinas de estado.

Ele permite organizar processos compostos por várias etapas, decisões, retries, esperas, paralelismo e tratamento de erro.

Em serverless, Step Functions evita que uma função Lambda precise chamar outra função diretamente em cadeias longas e difíceis de observar.

---

## Visão geral

AWS Step Functions faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## State Machine

Uma state machine define o fluxo.

Ela descreve estados e transições.

Estados podem:

* executar tarefa;
* tomar decisão;
* esperar;
* paralelizar;
* mapear itens;
* capturar erro;
* tentar novamente;
* finalizar.

---

## Por que Usar

Sem orquestração, um fluxo pode virar:


* Lambda A chama Lambda B
* Lambda B chama Lambda C
* Lambda C chama Lambda D


Esse desenho dificulta rastreamento e recuperação de falhas.

Com Step Functions, o fluxo fica explícito.

---

## Orquestração

Step Functions aplica [[Orquestração]].

Um componente central coordena a sequência das etapas.

Isso é útil quando o processo tem regras claras, compensações, branches e dependências.

---

## Exemplo de Pedido

Um workflow de pedido pode seguir:

1. validar carrinho;
2. reservar estoque;
3. processar pagamento;
4. emitir nota;
5. enviar e-mail;
6. compensar reserva se pagamento falhar.

Cada etapa pode ser uma função [[AWS Lambda]], uma chamada a serviço AWS ou uma integração externa.

---

## Express vs Standard

Em termos didáticos:

* Standard Workflows: duráveis, rastreáveis e adequados a processos que precisam de histórico mais longo.
* Express Workflows: alto volume, menor duração e menor custo por evento em certos cenários.

A escolha depende de duração, volume, necessidade de auditoria e custo.

---

## Observabilidade

Step Functions registra execução, estados, erros e transições.

Com [[Amazon CloudWatch]], a equipe acompanha falhas e desempenho do workflow.

---

## Cuidado

Nem todo fluxo precisa de Step Functions.

Se a lógica é simples, uma função Lambda ou evento direto pode bastar. Step Functions agrega muito quando há múltiplas etapas, retries, decisões ou compensações.

---

## Exemplo Prático

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige IAM, logs, retries, DLQ e idempotência.

---

## Cuidados importantes

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.
