Apache Kafka é uma plataforma distribuída de streaming de eventos.

Ela organiza eventos em tópicos particionados, permite múltiplos consumidores e mantém retenção por período ou tamanho.

Apache Kafka aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Apache Kafka deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Apache Kafka existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Modelo**

* producer: ↓.
* topic: ↓.
* partition: ↓.
* consumer group

**Uso**

* event streaming;
* logs;
* CDC;
* integração entre sistemas;
* pipelines analíticos;
* event sourcing;
* telemetria.

**AWS**

Na AWS, Kafka gerenciado aparece em [[Amazon MSK]].

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Diferença para Fila**

Em uma fila tradicional, a mensagem geralmente é consumida e removida.

Em Kafka, eventos permanecem por retenção, e consumidores controlam sua posição por offsets.

Isso permite que múltiplos consumidores leiam o mesmo fluxo de forma independente.

**Como Diferenciar**

* [[Amazon SQS|SQS]] é fila.
* SNS é pub/sub.
* EventBridge é barramento de eventos.
* MQ é broker gerenciado.
* MSK é Kafka gerenciado.
* Kinesis é streaming.

---

## Cuidados

Kafka é poderoso, mas exige maturidade operacional e modelagem de tópicos, partições e consumidores.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Amazon MSK]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
