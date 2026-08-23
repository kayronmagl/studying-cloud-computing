Delay Queues são filas do [[Amazon SQS]] que atrasam a disponibilidade de mensagens novas.

Quando uma mensagem é enviada, ela não fica imediatamente disponível para consumo.

Delay Queues aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Delay Queues deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Delay Queues existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Uso**

Delay Queues são úteis para:

* reprocessamento depois de espera;
* tarefas que não devem executar imediatamente;
* suavização de carga;
* workflows simples com atraso;
* evitar retry imediato.

---

## Exemplo prático

Uma aplicação agenda verificação de pagamento 5 minutos depois da criação do pedido.

Ela envia mensagem para uma fila com atraso.

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Diferença para Visibility Timeout**

Delay Queue atrasa a primeira entrega.

[[Visibility Timeout]] controla invisibilidade depois que a mensagem foi recebida.

**Como Diferenciar**

* [[Amazon SQS|SQS]] é fila.
* SNS é pub/sub.
* EventBridge é barramento de eventos.
* MQ é broker gerenciado.
* MSK é Kafka gerenciado.
* Kinesis é streaming.

---

## Cuidados

Para agendamentos complexos, [[EventBridge Scheduler]] pode ser mais adequado.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
- [[Visibility Timeout]]
- [[EventBridge Scheduler]]
