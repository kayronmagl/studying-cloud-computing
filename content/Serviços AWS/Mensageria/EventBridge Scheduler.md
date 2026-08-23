EventBridge Scheduler é o serviço de agendamento serverless da AWS para executar tarefas em horários definidos ou recorrentes.

Ele substitui muitos casos de cron gerenciado manualmente.

EventBridge Scheduler aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

EventBridge Scheduler deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

EventBridge Scheduler existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Uso**

Pode acionar:

* funções [[AWS Lambda]];
* filas [[Amazon SQS]];
* tópicos [[Amazon SNS]];
* [[APIs|APIs]];
* outros destinos compatíveis.

---

## Exemplo prático

Enviar mensagem para uma fila [[Amazon SQS|SQS]] todos os dias às 8h para iniciar processamento.

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Diferença para Delay Queue**

[[Delay Queues]] atrasam mensagens em uma fila por um intervalo.

EventBridge Scheduler agenda execuções pontuais ou recorrentes com maior flexibilidade.

**Como Diferenciar**

* [[Amazon SQS|SQS]] é fila.
* SNS é pub/sub.
* EventBridge é barramento de eventos.
* MQ é broker gerenciado.
* MSK é Kafka gerenciado.
* Kinesis é streaming.

---

## Cuidados

Agendamentos precisam de timezone, retries, permissões e monitoramento.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[AWS Lambda]]
- [[Amazon SQS]]
- [[Amazon SNS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon EventBridge]]
- [[Delay Queues]]
