Kafka Partitions são divisões de um tópico no [[Apache Kafka]].

Elas permitem paralelismo, distribuição e ordenação local.


Kafka Partitions aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Ordenação

Kafka garante ordem dentro de uma partição, não necessariamente entre partições diferentes.

---

## Chave

A chave do evento pode determinar para qual partição ele vai.

Eventos com a mesma chave podem ir para a mesma partição, preservando ordem por entidade.

---

## Paralelismo

Mais partições permitem mais consumidores em paralelo dentro de um [[Kafka Consumer Groups|consumer group]].

---

## Cuidado

Partições demais aumentam complexidade.

Partições de menos limitam paralelismo.

---

## Paralelismo na prática

Partições são a principal unidade de paralelismo em Kafka.

Se um tópico tem dez partições, um consumer group pode ter até dez consumidores trabalhando em paralelo com uma partição por consumidor.

---

## Ordenação por Partição

A ordem é preservada dentro da partição.

Se a ordem por pedido é importante, eventos do mesmo pedido devem usar a mesma chave para cair na mesma partição.

---

## Hot Partitions

Se uma chave concentra tráfego demais, uma partição pode ficar sobrecarregada.

Isso é chamado de hot partition.

Escolher boas chaves é parte essencial do desenho Kafka.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

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
