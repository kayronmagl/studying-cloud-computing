SNS Subscriptions conectam um [[SNS Topics|tópico SNS]] a um destino assinante.

Elas definem para onde mensagens publicadas no tópico serão entregues.

---

## Visão geral

SNS Subscriptions aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Destinos

Uma subscription pode apontar para:

* fila [[Amazon SQS]];
* função [[AWS Lambda]];
* endpoint HTTP/S;
* e-mail;
* SMS;
* outros destinos suportados.

---

## Confirmação

Alguns tipos de subscription exigem confirmação.

Isso evita que mensagens sejam enviadas para endpoints sem autorização.

---

## Filtros

Subscriptions podem usar [[SNS Message Filtering]] para receber apenas parte das mensagens.

---

## Cuidado

Cada assinante deve ter capacidade de processar o volume recebido.

Se um destino não suporta a carga, use SQS como buffer.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.
