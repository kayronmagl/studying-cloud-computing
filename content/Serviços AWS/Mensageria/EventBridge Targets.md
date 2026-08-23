EventBridge Targets são destinos para eventos roteados por regras do [[Amazon EventBridge]].

Uma regra pode entregar eventos para um ou mais targets.

EventBridge Targets aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

EventBridge Targets deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

EventBridge Targets existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Permissões**

EventBridge precisa de permissão para invocar ou entregar ao target.

Isso conecta mensageria com [[AWS Identity and Access Management (IAM)|IAM]].

---

## Exemplo prático

Targets podem incluir:

* [[AWS Lambda]];
* [[Amazon SQS]];
* [[Amazon SNS]];
* [[AWS Step Functions]];
* event buses;
* [[APIs|API]] destinations;
* outros serviços AWS compatíveis.

Evento `PagamentoAprovado` inicia um workflow no Step Functions e envia uma mensagem para uma fila [[Amazon SQS|SQS]].

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

Targets devem ser monitorados.

Falhas de entrega precisam de retry, DLQ ou estratégia de recuperação.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Amazon EventBridge]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Lambda]]
- [[Amazon SQS]]
- [[Amazon SNS]]
- [[AWS Step Functions]]
- [[Dead Letter Queue (DLQ)]]
