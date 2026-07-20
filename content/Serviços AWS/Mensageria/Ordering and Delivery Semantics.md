Ordering and Delivery Semantics descreve garantias de ordem e entrega de mensagens.

Essas garantias são centrais em mensageria porque diferentes serviços fazem trade-offs diferentes entre escala, disponibilidade, ordem e duplicidade.

---

## Visão geral

Ordering and Delivery Semantics aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Garantias Comuns

* entrega pelo menos uma vez;
* entrega no máximo uma vez;
* processamento exatamente uma vez em contextos específicos;
* ordenação por fila;
* ordenação por grupo;
* ordenação por partição;
* deduplicação.

---

## Exemplos AWS

[[SQS Standard Queues]] priorizam alta escala e usam [[At-Least-Once Delivery]].

[[SQS FIFO Queues]] priorizam ordem e deduplicação.

[[Apache Kafka]] preserva ordem por partição.

[[Amazon Kinesis Data Streams]] organiza registros por shards.

---

## Cuidado

Garantia global de ordem geralmente reduz paralelismo.

Para escalar, muitas arquiteturas preservam ordem apenas por entidade, grupo, chave ou partição.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.
