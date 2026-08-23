SNS Subscriptions conectam um [[SNS Topics|tópico SNS]] a um destino assinante.

Elas definem para onde mensagens publicadas no tópico serão entregues.

SNS Subscriptions aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

SNS Subscriptions deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

---

## Por que existe

SNS Subscriptions existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Destinos**

Uma subscription pode apontar para:

* fila [[Amazon SQS]];
* função [[AWS Lambda]];
* endpoint HTTP/S;
* e-mail;
* SMS;
* outros destinos suportados.

**Confirmação**

Alguns tipos de subscription exigem confirmação.

Isso evita que mensagens sejam enviadas para endpoints sem autorização.

**Filtros**

Subscriptions podem usar [[SNS Message Filtering]] para receber apenas parte das mensagens.

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

Não confunda fila, tópico, evento e stream. Fila distribui mensagens para processamento, tópico publica para assinantes, evento descreve algo ocorrido e stream preserva sequência de registros para consumo contínuo.

---

## Cuidados

Cada assinante deve ter capacidade de processar o volume recebido.

Se um destino não suporta a carga, use [[Amazon SQS|SQS]] como buffer.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

---

## Relação com outras notas

- [[SNS Topics]]
- [[Amazon SQS]]
- [[AWS Lambda]]
- [[SNS Message Filtering]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
