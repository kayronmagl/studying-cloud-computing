SQS Standard Queues são filas padrão do [[Amazon SQS]].

Elas oferecem alta escala e entrega pelo menos uma vez.

---

## Visão geral

SQS Standard Queues aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Características

* alta taxa de throughput;
* entrega pelo menos uma vez;
* melhor esforço de ordenação;
* múltiplos produtores e consumidores;
* escalabilidade gerenciada.

---

## At-Least-Once

Em Standard Queues, uma mensagem pode ser entregue mais de uma vez.

Isso acontece porque o serviço prioriza disponibilidade e escala.

Por isso, consumidores devem aplicar [[Idempotência]].

---

## Quando Usar

Use Standard Queues quando:

* throughput é prioridade;
* a ordem exata não é crítica;
* duplicidade pode ser tratada;
* o workload precisa de alta escala.

---

## Exemplo

Processamento de imagens, envio de e-mails, atualização de analytics e tarefas independentes geralmente funcionam bem com filas Standard.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

---

## Como entender isso

Este conceito pertence ao módulo de mensageria na AWS.

## Ponto central

Mensageria desacopla produtores e consumidores.

## Como Diferenciar

* SQS é fila.
* SNS é pub/sub.
* EventBridge é barramento de eventos.
* MQ é broker gerenciado.
* MSK é Kafka gerenciado.
* Kinesis é streaming.

## Cuidado importante

Mensageria exige idempotência, retries, DLQ e observabilidade.
