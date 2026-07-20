EventBridge Targets são destinos para eventos roteados por regras do [[Amazon EventBridge]].

Uma regra pode entregar eventos para um ou mais targets.

---

## Visão geral

EventBridge Targets aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Exemplos

Targets podem incluir:

* [[AWS Lambda]];
* [[Amazon SQS]];
* [[Amazon SNS]];
* [[AWS Step Functions]];
* event buses;
* API destinations;
* outros serviços AWS compatíveis.

---

## Permissões

EventBridge precisa de permissão para invocar ou entregar ao target.

Isso conecta mensageria com [[AWS Identity and Access Management (IAM)|IAM]].

---

## Exemplo

Evento `PagamentoAprovado` inicia um workflow no Step Functions e envia uma mensagem para uma fila SQS.

---

## Cuidado

Targets devem ser monitorados.

Falhas de entrega precisam de retry, DLQ ou estratégia de recuperação.

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
