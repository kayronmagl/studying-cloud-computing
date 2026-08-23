Message Retention é o período pelo qual o [[Amazon SQS]] mantém mensagens que ainda não foram deletadas.

Depois que o período expira, a mensagem pode ser removida.

Message Retention aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Message Retention deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Retenção define por quanto tempo uma mensagem pode aguardar processamento.

Se consumidores ficam fora por mais tempo que a retenção, mensagens podem ser perdidas.

---

## Como funciona

**Uso**

Retenção maior ajuda em falhas longas, manutenção e backlogs.

Retenção menor reduz armazenamento de mensagens antigas.

---

## Exemplo prático

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

Retenção não é arquivamento permanente.

Se mensagens precisam ser preservadas por auditoria, use armazenamento apropriado, como [[Amazon S3]].

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

**Relação com DLQ**

Mensagens em [[Dead Letter Queue (DLQ)]] também possuem retenção.

É importante definir retenção suficiente para investigação.
