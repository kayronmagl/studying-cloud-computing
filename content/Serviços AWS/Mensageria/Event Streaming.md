Event Streaming é o processamento contínuo de eventos conforme eles são produzidos.

Em vez de esperar lotes periódicos, sistemas leem e processam dados em fluxo.


Event Streaming aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Exemplos

* logs de aplicação;
* eventos de clique;
* telemetria IoT;
* transações;
* métricas;
* eventos de pedidos.

---

## AWS

Serviços importantes:

* [[Amazon MSK]];
* [[Amazon Kinesis Data Streams]];
* [[Amazon Data Firehose]];
* [[Amazon Managed Service for Apache Flink]].

---

## Diferença para Fila

Fila costuma representar trabalho a ser processado.

Stream representa sequência contínua de eventos com retenção e múltiplos consumidores.

---

## Cuidado

Streaming exige pensar em ordenação, retenção, atraso, throughput e reprocessamento.

---

## Diferença para Eventos Isolados

Em event streaming, o foco é o fluxo contínuo.

Não se trata apenas de reagir a um evento individual, mas de processar muitos eventos ao longo do tempo.

---

## Exemplos de Uso

* monitoramento em tempo real;
* fraude;
* clickstream;
* telemetria IoT;
* logs de aplicação;
* métricas operacionais;
* pipelines analíticos.

---

## Relação com Kinesis e Kafka

[[Amazon Kinesis Data Streams]] e [[Amazon MSK]] são serviços centrais para event streaming na AWS.

Eles permitem múltiplos consumidores e processamento contínuo.

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
