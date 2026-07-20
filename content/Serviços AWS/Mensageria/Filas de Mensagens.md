Filas de Mensagens armazenam mensagens entre produtores e consumidores.

O produtor envia uma mensagem para a fila. O consumidor lê e processa quando puder.

---

## Visão geral

Filas de Mensagens aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Problema que Resolve

Filas resolvem diferença de ritmo.

Um produtor pode gerar trabalho rapidamente, enquanto consumidores processam mais devagar.

A fila absorve o pico.

---

## Modelo

* produtor: ↓.
* fila: ↓.
* consumidor


---

## Vantagens

* desacoplamento;
* buffer;
* retries;
* processamento assíncrono;
* absorção de picos;
* isolamento de falhas;
* suporte a DLQ.

---

## AWS

Na AWS, o serviço principal de fila gerenciada é [[Amazon SQS]].

---

## Cuidado

Filas podem crescer indefinidamente se consumidores não acompanham.

É necessário monitorar tamanho da fila, idade das mensagens, erros e DLQ com [[Amazon CloudWatch]].

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
