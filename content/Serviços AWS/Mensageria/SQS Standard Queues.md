[[Amazon SQS|SQS]] Standard Queues são filas padrão do [[Amazon SQS]].

Elas oferecem alta escala e entrega pelo menos uma vez.

[[Amazon SQS|SQS]] Standard Queues aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

SQS Standard Queues deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

[[Amazon SQS|SQS]] Standard Queues existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Características**

* alta taxa de throughput;
* entrega pelo menos uma vez;
* melhor esforço de ordenação;
* múltiplos produtores e consumidores;
* escalabilidade gerenciada.

**At-Least-Once**

Em Standard Queues, uma mensagem pode ser entregue mais de uma vez.

Isso acontece porque o serviço prioriza disponibilidade e escala.

Por isso, consumidores devem aplicar [[Idempotência]].

---

## Exemplo prático

Processamento de imagens, envio de e-mails, atualização de analytics e tarefas independentes geralmente funcionam bem com filas Standard.

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Quando Usar**

Use Standard Queues quando:

* throughput é prioridade;
* a ordem exata não é crítica;
* duplicidade pode ser tratada;
* o workload precisa de alta escala.

**Como Diferenciar**

* [[Amazon SQS|SQS]] é fila.
* SNS é pub/sub.
* EventBridge é barramento de eventos.
* MQ é broker gerenciado.
* MSK é Kafka gerenciado.
* Kinesis é streaming.

---

## Cuidados

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Amazon SQS]]
- [[Idempotência]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
