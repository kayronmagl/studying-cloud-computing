EventBridge Event Bus é o barramento que recebe eventos no [[Amazon EventBridge]].

Ele funciona como um roteador de eventos.

EventBridge Event Bus aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

EventBridge Event Bus deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

EventBridge Event Bus existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Tipos**

Existem barramentos como:

* default event bus;
* custom event bus;
* partner event bus.

**Função**

O event bus recebe eventos de fontes e os disponibiliza para regras.

As regras avaliam padrões e enviam eventos a targets.

---

## Exemplo prático

Uma aplicação publica `PedidoCriado` em um custom event bus.

Regras podem enviar esse evento para [[AWS Lambda|Lambda]], Step Functions, [[Amazon SQS|SQS]] ou SNS.

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

Separe barramentos quando houver domínios, permissões ou responsabilidades diferentes.

Um barramento único para tudo pode ficar difícil de governar.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Amazon EventBridge]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
