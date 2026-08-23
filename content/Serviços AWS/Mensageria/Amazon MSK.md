Amazon MSK significa Amazon Managed Streaming for Apache Kafka.

É o serviço gerenciado da AWS para executar [[Apache Kafka]].

A documentação da AWS descreve MSK como serviço totalmente gerenciado que permite criar e executar aplicações que usam Apache Kafka para processar dados de streaming.

Amazon MSK aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Amazon MSK deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Amazon MSK existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Kafka como Streaming**

Kafka não é apenas uma fila.

Ele é uma plataforma de streaming de eventos baseada em tópicos particionados, retenção e grupos de consumidores.

**Componentes**

* [[Kafka Topics]];
* [[Kafka Partitions]];
* [[Kafka Consumer Groups]];
* brokers;
* producers;
* consumers;
* offsets.

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Quando Usar**

Use MSK quando precisa de:

* Kafka gerenciado;
* pipelines de eventos;
* event streaming;
* integração de dados;
* retenção de eventos;
* múltiplos consumidores independentes;
* compatibilidade com ecossistema Kafka.

**Diferença para Kinesis**

[[Amazon Kinesis Data Streams]] é streaming nativo AWS.

MSK é Kafka gerenciado.

A escolha depende de ecossistema, compatibilidade, operação, equipe e requisitos.

**Como Diferenciar**

* [[Amazon SQS|SQS]] é fila.
* SNS é pub/sub.
* EventBridge é barramento de eventos.
* MQ é broker gerenciado.
* MSK é Kafka gerenciado.
* Kinesis é streaming.

---

## Cuidados

MSK reduz gerenciamento do cluster, mas Kafka continua exigindo entendimento de partições, consumer groups, retenção, lag, brokers e throughput.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Apache Kafka]]
- [[Kafka Topics]]
- [[Kafka Partitions]]
- [[Kafka Consumer Groups]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
- [[Amazon Kinesis Data Streams]]
