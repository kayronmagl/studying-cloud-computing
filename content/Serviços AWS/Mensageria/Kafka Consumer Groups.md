Kafka Consumer Groups são grupos de consumidores que dividem a leitura das partições de tópicos Kafka.

Dentro de um grupo, cada partição é consumida por apenas um consumidor por vez.


Kafka Consumer Groups aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Função

Consumer groups permitem escalar consumo.

Se um tópico possui várias partições, múltiplos consumidores podem processar em paralelo.

---

## Múltiplos Grupos

Grupos diferentes podem ler o mesmo tópico independentemente.

Isso permite que pagamentos, analytics e auditoria consumam o mesmo fluxo sem competir.

---

## Offset

Cada grupo mantém sua posição de leitura.

---

## Cuidado

Se houver mais consumidores que partições, consumidores extras podem ficar ociosos.

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
