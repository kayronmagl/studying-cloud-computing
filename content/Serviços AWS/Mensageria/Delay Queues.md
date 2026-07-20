Delay Queues são filas do [[Amazon SQS]] que atrasam a disponibilidade de mensagens novas.

Quando uma mensagem é enviada, ela não fica imediatamente disponível para consumo.

---

## Visão geral

Delay Queues aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Uso

Delay Queues são úteis para:

* reprocessamento depois de espera;
* tarefas que não devem executar imediatamente;
* suavização de carga;
* workflows simples com atraso;
* evitar retry imediato.

---

## Diferença para Visibility Timeout

Delay Queue atrasa a primeira entrega.

[[Visibility Timeout]] controla invisibilidade depois que a mensagem foi recebida.

---

## Exemplo

Uma aplicação agenda verificação de pagamento 5 minutos depois da criação do pedido.

Ela envia mensagem para uma fila com atraso.

---

## Cuidado

Para agendamentos complexos, [[EventBridge Scheduler]] pode ser mais adequado.

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
