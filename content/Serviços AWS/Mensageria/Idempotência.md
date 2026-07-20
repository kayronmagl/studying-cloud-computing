Idempotência é a propriedade de uma operação produzir o mesmo resultado mesmo se for executada mais de uma vez.

Em mensageria, idempotência é fundamental porque mensagens podem ser entregues novamente, eventos podem ser repetidos e consumidores podem falhar depois de executar parte da lógica.

---

## Visão geral

Idempotência aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Exemplo

Um evento `PagamentoAprovado` chega duas vezes.

Uma aplicação idempotente reconhece que aquele pagamento já foi processado e não cobra novamente.

---

## Estratégias

* usar ID único de mensagem;
* registrar eventos processados;
* usar constraints no banco;
* aplicar chaves idempotentes;
* verificar estado antes de alterar;
* tornar operações de escrita seguras.

---

## Relação com SQS

[[SQS Standard Queues]] podem entregar mensagens mais de uma vez.

Logo, consumidores precisam ser idempotentes.

---

## Relação com Eventos

Em [[Amazon EventBridge]], consumidores também devem tolerar repetição, atraso e reprocessamento.

---

## Erro Comum

Assumir que “isso nunca vai repetir”.

Em sistemas distribuídos, a postura correta é projetar para duplicidade.

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
