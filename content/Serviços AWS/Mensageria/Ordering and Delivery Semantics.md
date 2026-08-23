Ordering and Delivery Semantics descreve garantias de ordem e entrega de mensagens.

Essas garantias são centrais em mensageria porque diferentes serviços fazem trade-offs diferentes entre escala, disponibilidade, ordem e duplicidade.

Ordering and Delivery Semantics aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Ordering and Delivery Semantics deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

---

## Por que existe

Ordering and Delivery Semantics existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Garantias Comuns**

* entrega pelo menos uma vez;
* entrega no máximo uma vez;
* processamento exatamente uma vez em contextos específicos;
* ordenação por fila;
* ordenação por grupo;
* ordenação por partição;
* deduplicação.

**Exemplos AWS**

[[SQS Standard Queues]] priorizam alta escala e usam [[At-Least-Once Delivery]].

[[SQS FIFO Queues]] priorizam ordem e deduplicação.

[[Apache Kafka]] preserva ordem por partição.

[[Amazon Kinesis Data Streams]] organiza registros por shards.

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

Não confunda fila, tópico, evento e stream. Fila distribui mensagens para processamento, tópico publica para assinantes, evento descreve algo ocorrido e stream preserva sequência de registros para consumo contínuo.

---

## Cuidados

Garantia global de ordem geralmente reduz paralelismo.

Para escalar, muitas arquiteturas preservam ordem apenas por entidade, grupo, chave ou partição.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

---

## Relação com outras notas

- [[SQS Standard Queues]]
- [[At-Least-Once Delivery]]
- [[SQS FIFO Queues]]
- [[Apache Kafka]]
- [[Amazon Kinesis Data Streams]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
