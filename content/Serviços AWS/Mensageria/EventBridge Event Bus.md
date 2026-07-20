EventBridge Event Bus é o barramento que recebe eventos no [[Amazon EventBridge]].

Ele funciona como um roteador de eventos.

---

## Visão geral

EventBridge Event Bus aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Tipos

Existem barramentos como:

* default event bus;
* custom event bus;
* partner event bus.

---

## Função

O event bus recebe eventos de fontes e os disponibiliza para regras.

As regras avaliam padrões e enviam eventos a targets.

---

## Exemplo

Uma aplicação publica `PedidoCriado` em um custom event bus.

Regras podem enviar esse evento para Lambda, Step Functions, SQS ou SNS.

---

## Cuidado

Separe barramentos quando houver domínios, permissões ou responsabilidades diferentes.

Um barramento único para tudo pode ficar difícil de governar.

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
