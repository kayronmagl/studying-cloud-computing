Apache Kafka é uma plataforma distribuída de streaming de eventos.

Ela organiza eventos em tópicos particionados, permite múltiplos consumidores e mantém retenção por período ou tamanho.


Apache Kafka aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Modelo

* producer: ↓.
* topic: ↓.
* partition: ↓.
* consumer group


---

## Diferença para Fila

Em uma fila tradicional, a mensagem geralmente é consumida e removida.

Em Kafka, eventos permanecem por retenção, e consumidores controlam sua posição por offsets.

Isso permite que múltiplos consumidores leiam o mesmo fluxo de forma independente.

---

## Uso

* event streaming;
* logs;
* CDC;
* integração entre sistemas;
* pipelines analíticos;
* event sourcing;
* telemetria.

---

## AWS

Na AWS, Kafka gerenciado aparece em [[Amazon MSK]].

---

## Cuidado

Kafka é poderoso, mas exige maturidade operacional e modelagem de tópicos, partições e consumidores.

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
