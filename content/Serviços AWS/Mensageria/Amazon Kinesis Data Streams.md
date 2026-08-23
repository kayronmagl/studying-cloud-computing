Amazon Kinesis Data Streams é o serviço de streaming em tempo real da AWS.

Ele permite coletar e processar grandes fluxos de registros de dados em tempo real.

A documentação da AWS descreve Kinesis Data Streams como serviço para coletar e processar grandes streams de registros em tempo real, com aplicações que leem dados de streams compostos por shards.

Amazon Kinesis Data Streams aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Amazon Kinesis Data Streams deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Amazon Kinesis Data Streams existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Modelo**

* producer: ↓.
* data stream: ↓.
* shards: ↓.
* consumer

**Usos**

* logs;
* métricas;
* eventos de aplicação;
* telemetria;
* IoT;
* clickstream;
* analytics em tempo real;
* detecção de anomalias.

**Componentes**

* [[Kinesis Shards]];
* [[Data Records]];
* [[Producers and Consumers]];
* [[Stream Processing]].

**Fluxo contínuo de eventos**

[[Event Streaming]] aparece quando dados chegam continuamente e precisam ser processados em tempo real.

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Diferença para [[Amazon SQS|SQS]]**

[[Amazon SQS|SQS]] é fila.

Kinesis é stream.

Em stream, múltiplos consumidores podem ler registros por janela de retenção.

**Como Diferenciar**

* [[Amazon SQS|SQS]] é fila.
* SNS é pub/sub.
* EventBridge é barramento de eventos.
* MQ é broker gerenciado.
* MSK é Kafka gerenciado.
* Kinesis é streaming.

---

## Cuidados

A capacidade depende de shards, throughput, retenção e consumidores.

É preciso monitorar lag, erros e limites.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Kinesis Shards]]
- [[Data Records]]
- [[Producers and Consumers]]
- [[Stream Processing]]
- [[Event Streaming]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
