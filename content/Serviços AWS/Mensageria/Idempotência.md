Idempotência é a propriedade de uma operação produzir o mesmo resultado mesmo se for executada mais de uma vez.

Em mensageria, idempotência é fundamental porque mensagens podem ser entregues novamente, eventos podem ser repetidos e consumidores podem falhar depois de executar parte da lógica.

Idempotência aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Idempotência deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Idempotência existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Estratégias**

* usar ID único de mensagem;
* registrar eventos processados;
* usar constraints no banco;
* aplicar chaves idempotentes;
* verificar estado antes de alterar;
* tornar operações de escrita seguras.

---

## Exemplo prático

Um evento `PagamentoAprovado` chega duas vezes.

Uma aplicação idempotente reconhece que aquele pagamento já foi processado e não cobra novamente.

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

**Erro Comum**

Assumir que “isso nunca vai repetir”.

Em sistemas distribuídos, a postura correta é projetar para duplicidade.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

**Relação com [[Amazon SQS|SQS]]**

[[SQS Standard Queues]] podem entregar mensagens mais de uma vez.

Logo, consumidores precisam ser idempotentes.

**Relação com Eventos**

Em [[Amazon EventBridge]], consumidores também devem tolerar repetição, atraso e reprocessamento.
