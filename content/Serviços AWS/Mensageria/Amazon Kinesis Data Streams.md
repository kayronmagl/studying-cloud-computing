Amazon Kinesis Data Streams é o serviço de streaming em tempo real da AWS.

Ele permite coletar e processar grandes fluxos de registros de dados em tempo real.

A documentação da AWS descreve Kinesis Data Streams como serviço para coletar e processar grandes streams de registros em tempo real, com aplicações que leem dados de streams compostos por shards.

---

## Visão geral

Amazon Kinesis Data Streams aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Modelo

* producer: ↓.
* data stream: ↓.
* shards: ↓.
* consumer


---

## Usos

* logs;
* métricas;
* eventos de aplicação;
* telemetria;
* IoT;
* clickstream;
* analytics em tempo real;
* detecção de anomalias.

---

## Componentes

* [[Kinesis Shards]];
* [[Data Records]];
* [[Producers and Consumers]];
* [[Stream Processing]].

---

## Diferença para SQS

SQS é fila.

Kinesis é stream.

Em stream, múltiplos consumidores podem ler registros por janela de retenção.

---

## Cuidado

A capacidade depende de shards, throughput, retenção e consumidores.

É preciso monitorar lag, erros e limites.

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

---

## Fluxo contínuo de eventos

[[Event Streaming]] aparece quando dados chegam continuamente e precisam ser processados em tempo real.
