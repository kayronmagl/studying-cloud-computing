Filas de Mensagens armazenam mensagens entre produtores e consumidores.

O produtor envia uma mensagem para a fila. O consumidor lê e processa quando puder.

Filas de Mensagens aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Filas de Mensagens deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Filas resolvem diferença de ritmo.

Um produtor pode gerar trabalho rapidamente, enquanto consumidores processam mais devagar.

A fila absorve o pico.

* desacoplamento;
* buffer;
* retries;
* processamento assíncrono;
* absorção de picos;
* isolamento de falhas;
* suporte a DLQ.

---

## Como funciona

**Modelo**

* produtor: ↓.
* fila: ↓.
* consumidor

**AWS**

Na AWS, o serviço principal de fila gerenciada é [[Amazon SQS]].

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Como Diferenciar**

* [[Amazon SQS|SQS]] é fila.
* SNS é pub/sub.
* EventBridge é barramento de eventos.
* MQ é broker gerenciado.
* MSK é Kafka gerenciado.
* Kinesis é streaming.

---

## Cuidados

Filas podem crescer indefinidamente se consumidores não acompanham.

É necessário monitorar tamanho da fila, idade das mensagens, erros e DLQ com [[Amazon CloudWatch]].

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
- [[Amazon CloudWatch]]
