Fanout é o padrão em que uma mensagem publicada uma vez é distribuída para múltiplos consumidores.

Na AWS, um padrão comum é usar [[Amazon SNS]] publicando para múltiplas filas [[Amazon SQS]].


Fanout aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Modelo

* SNS Topic: ↓.
* SQS Pagamento
* SQS Estoque
* SQS Email
* SQS Analytics


Cada fila recebe uma cópia da mensagem e processa no seu ritmo.

---

## Benefício

O produtor não precisa conhecer todos os consumidores.

Novos consumidores podem ser adicionados sem alterar o produtor.

---

## Exemplo

Quando um pedido é criado, vários fluxos podem reagir:

* processar pagamento;
* reservar estoque;
* enviar e-mail;
* atualizar analytics;
* emitir nota.

---

## Cuidado

Fanout aumenta a necessidade de observabilidade.

É preciso saber quais consumidores receberam, falharam ou atrasaram.

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
