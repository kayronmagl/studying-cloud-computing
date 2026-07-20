Amazon SNS significa Amazon Simple Notification Service.

É o serviço de publicação e assinatura da AWS. Ele permite publicar mensagens em tópicos e entregá-las a múltiplos assinantes.

A documentação da AWS descreve o cenário fanout como a replicação de uma mensagem publicada em um tópico SNS para múltiplos endpoints, como filas SQS, funções Lambda e endpoints HTTP/S.

---

## Visão geral

Amazon SNS aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Modelo

* publicador: ↓.
* SNS Topic: ↓.
* assinante A
* assinante B
* assinante C


---

## Componentes

* [[SNS Topics]];
* [[SNS Subscriptions]];
* [[SNS Message Filtering]];
* [[SNS FIFO Topics]].

---

## Fanout

[[Fanout]] é um dos usos mais comuns.

Uma mensagem publicada uma vez pode ser entregue a várias filas SQS, permitindo processamento paralelo independente.

---

## Quando Usar

Use SNS quando:

* múltiplos consumidores precisam receber a mesma mensagem;
* notificações precisam ser distribuídas;
* filas precisam receber cópias;
* aplicações precisam de pub/sub simples;
* fanout é necessário.

---

## Cuidado

SNS empurra mensagens para assinantes.

Se o assinante falha, é necessário entender política de retry, DLQ e destino.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

---

## Explicação principal

Amazon SNS é o serviço de publicação e assinatura.

Ele usa tópicos. Um publicador envia mensagem para o tópico, e vários assinantes recebem.

## Modelo na prática

* publisher: ↓.
* topic: ↓.
* assinantes

## Assinantes Comuns

* SQS;
* Lambda;
* HTTP/S;
* e-mail;
* SMS.

## Quando Usar na prática

Use SNS quando vários sistemas precisam reagir ao mesmo evento.

## Cuidado importante

SNS empurra mensagens. Se o destino não suporta carga, combine SNS com SQS para criar buffer.

---

## Publicação e assinatura

O SNS usa o modelo [[Publish Subscribe (Pub Sub)]], em que uma mensagem publicada pode chegar a vários assinantes.
