Producers and Consumers são produtores e consumidores de mensagens, eventos ou registros.

Produtores escrevem. Consumidores leem e processam.

---

## Visão geral

Producers and Consumers aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Em Filas

No [[Amazon SQS]], produtores enviam mensagens para filas e consumidores removem mensagens depois de processar.

---

## Em Streams

No [[Amazon Kinesis Data Streams]], producers escrevem registros e consumers leem registros por shard.

---

## Em Kafka

No [[Apache Kafka]], producers escrevem em tópicos e consumers leem por consumer groups.

---

## Cuidado

O ritmo de produção e consumo precisa ser monitorado.

Se produtores são mais rápidos que consumidores por muito tempo, backlog cresce.

---

## Ritmo de Produção e Consumo

A diferença entre velocidade de produção e consumo define saúde do sistema.

Se producers são mais rápidos por muito tempo, surge [[Backpressure]].

---

## Exemplos

Em [[Amazon SQS]], producers enviam mensagens e consumers deletam depois de processar.

Em [[Amazon Kinesis Data Streams]], producers enviam registros e consumers leem continuamente.

Em [[Apache Kafka]], producers escrevem em tópicos e consumers leem por grupos.

---

## Cuidado na prática

Produtores e consumidores devem ter contratos claros de mensagem, versionamento e tratamento de falha.

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
