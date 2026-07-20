Amazon Data Firehose é o serviço da AWS para capturar, transformar e entregar dados de streaming para destinos.

Ele é usado para entregar dados em serviços como [[Amazon S3]], [[Amazon Redshift]], [[Amazon OpenSearch Service]] e destinos HTTP compatíveis.

---

## Visão geral

Amazon Data Firehose aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Papel

Firehose é mais voltado à entrega gerenciada de streams do que à criação de aplicações consumidoras complexas.

---

## Uso

* logs para S3;
* eventos para data lake;
* dados para Redshift;
* logs para OpenSearch;
* entrega contínua com transformação opcional.

---

## Diferença para Kinesis Data Streams

[[Amazon Kinesis Data Streams]] é stream para produtores e consumidores customizados.

Firehose é entrega gerenciada para destinos.

---

## Cuidado

Firehose é excelente para entrega, mas não substitui processamento complexo de stream. Para isso, avalie [[Amazon Managed Service for Apache Flink]].

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
