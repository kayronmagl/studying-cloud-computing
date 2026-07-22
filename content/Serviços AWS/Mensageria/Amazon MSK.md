Amazon MSK significa Amazon Managed Streaming for Apache Kafka.

É o serviço gerenciado da AWS para executar [[Apache Kafka]].

A documentação da AWS descreve MSK como serviço totalmente gerenciado que permite criar e executar aplicações que usam Apache Kafka para processar dados de streaming.


Amazon MSK aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Kafka como Streaming

Kafka não é apenas uma fila.

Ele é uma plataforma de streaming de eventos baseada em tópicos particionados, retenção e grupos de consumidores.

---

## Componentes

* [[Kafka Topics]];
* [[Kafka Partitions]];
* [[Kafka Consumer Groups]];
* brokers;
* producers;
* consumers;
* offsets.

---

## Quando Usar

Use MSK quando precisa de:

* Kafka gerenciado;
* pipelines de eventos;
* event streaming;
* integração de dados;
* retenção de eventos;
* múltiplos consumidores independentes;
* compatibilidade com ecossistema Kafka.

---

## Diferença para Kinesis

[[Amazon Kinesis Data Streams]] é streaming nativo AWS.

MSK é Kafka gerenciado.

A escolha depende de ecossistema, compatibilidade, operação, equipe e requisitos.

---

## Cuidado

MSK reduz gerenciamento do cluster, mas Kafka continua exigindo entendimento de partições, consumer groups, retenção, lag, brokers e throughput.

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
