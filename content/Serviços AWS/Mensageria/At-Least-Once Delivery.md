At-Least-Once Delivery significa que uma mensagem será entregue uma ou mais vezes.

O sistema tenta garantir que a mensagem não seja perdida, aceitando a possibilidade de duplicidade.


At-Least-Once Delivery aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Exemplo

[[Amazon SQS]] Standard Queues usam esse modelo.

Uma mensagem pode ser entregue para o consumidor, processada, mas por falha de confirmação, reaparecer na fila.

---

## Consequência

Consumidores precisam ser idempotentes.

Isso significa que processar a mesma mensagem duas vezes não deve corromper o sistema.

---

## Relação com Idempotência

[[Idempotência]] é a técnica que torna at-least-once seguro.

Sem idempotência, duplicidade pode gerar cobranças duplicadas, e-mails repetidos ou estados incorretos.

---

## Trade-off

At-least-once favorece durabilidade e disponibilidade.

O custo é lidar com duplicidade.

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
