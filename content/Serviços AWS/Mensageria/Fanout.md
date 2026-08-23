Fanout é o padrão em que uma mensagem publicada uma vez é distribuída para múltiplos consumidores.

Na AWS, um padrão comum é usar [[Amazon SNS]] publicando para múltiplas filas [[Amazon SQS]].

Fanout aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Fanout deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

O produtor não precisa conhecer todos os consumidores.

Novos consumidores podem ser adicionados sem alterar o produtor.

---

## Como funciona

**Modelo**

* SNS Topic: ↓.
* [[Amazon SQS|SQS]] Pagamento
* [[Amazon SQS|SQS]] Estoque
* [[Amazon SQS|SQS]] Email
* [[Amazon SQS|SQS]] Analytics

Cada fila recebe uma cópia da mensagem e processa no seu ritmo.

---

## Exemplo prático

Quando um pedido é criado, vários fluxos podem reagir:

* processar pagamento;
* reservar estoque;
* enviar e-mail;
* atualizar analytics;
* emitir nota.

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

Fanout aumenta a necessidade de observabilidade.

É preciso saber quais consumidores receberam, falharam ou atrasaram.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Amazon SNS]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon EventBridge]]
