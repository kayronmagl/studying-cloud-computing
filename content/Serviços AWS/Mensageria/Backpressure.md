Backpressure é a pressão de retorno que ocorre quando consumidores não conseguem acompanhar o ritmo dos produtores.

Em sistemas de mensageria, isso aparece como crescimento de fila, aumento de lag ou atraso no processamento.


Backpressure aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Exemplo

Uma API publica mil mensagens por segundo.

Os consumidores processam apenas cem por segundo.

O backlog cresce.

---

## Onde Aparece

* [[Amazon SQS]]: tamanho e idade da fila aumentam.
* [[Amazon MSK]]: consumer lag aumenta.
* [[Amazon Kinesis Data Streams]]: consumidores ficam atrasados.
* [[Amazon Data Firehose]]: buffers e entrega podem atrasar.

---

## Como Lidar

* aumentar consumidores;
* escalar workers;
* aplicar rate limiting;
* usar filas;
* ajustar shards/partições;
* otimizar processamento;
* aplicar backoff;
* separar fluxos críticos.

---

## Cuidado

Backpressure ignorado vira indisponibilidade, perda de dados, custo ou falha em cascata.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.
