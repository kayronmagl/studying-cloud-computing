SQS FIFO Queues são filas do [[Amazon SQS]] que preservam ordem e oferecem deduplicação dentro do modelo FIFO.

FIFO significa First In, First Out.

---

## Visão geral

SQS FIFO Queues aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Características

* ordem estrita dentro de grupos de mensagens;
* deduplicação;
* processamento mais controlado;
* nomes de fila com sufixo `.fifo`;
* uso de Message Group ID.

---

## Message Group ID

O Message Group ID define a sequência de ordenação.

Mensagens com o mesmo grupo são processadas em ordem.

Grupos diferentes podem ser processados em paralelo.

---

## Quando Usar

Use FIFO quando ordem importa:

* transações financeiras;
* atualização de estado;
* pedidos que precisam sequência;
* workflows com eventos ordenados por entidade.

---

## Cuidado

FIFO pode ter throughput menor ou exigir desenho cuidadoso de grupos.

Se tudo usa o mesmo Message Group ID, paralelismo fica limitado.
---

## Nuance sobre Exactly-Once

FIFO ajuda a evitar duplicidade no envio e preserva ordem por grupo de mensagens, mas a aplicação ainda deve ser cuidadosa.

Em sistemas distribuídos, falhas de consumidor, timeouts, retries externos e efeitos colaterais podem exigir [[Idempotência]] mesmo quando a fila oferece deduplicação.

Por isso, a interpretação correta é:


* SQS FIFO reduz duplicidade e preserva ordem por grupo: mas consumidores críticos ainda devem ser idempotentes.


---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

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
