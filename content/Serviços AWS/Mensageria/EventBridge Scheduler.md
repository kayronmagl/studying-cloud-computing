EventBridge Scheduler é o serviço de agendamento serverless da AWS para executar tarefas em horários definidos ou recorrentes.

Ele substitui muitos casos de cron gerenciado manualmente.

---

## Visão geral

EventBridge Scheduler aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Uso

Pode acionar:

* funções [[AWS Lambda]];
* filas [[Amazon SQS]];
* tópicos [[Amazon SNS]];
* APIs;
* outros destinos compatíveis.

---

## Exemplo

Enviar mensagem para uma fila SQS todos os dias às 8h para iniciar processamento.

---

## Diferença para Delay Queue

[[Delay Queues]] atrasam mensagens em uma fila por um intervalo.

EventBridge Scheduler agenda execuções pontuais ou recorrentes com maior flexibilidade.

---

## Cuidado

Agendamentos precisam de timezone, retries, permissões e monitoramento.

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
