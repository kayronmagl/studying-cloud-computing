Kafka Topics são categorias lógicas de eventos no [[Apache Kafka]].

Produtores escrevem eventos em tópicos. Consumidores leem eventos desses tópicos.

Kafka Topics aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Kafka Topics deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Kafka Topics existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Partições**

Tópicos são divididos em [[Kafka Partitions]].

Partições permitem paralelismo e ordenação dentro de cada partição.

**Retenção**

Eventos permanecem no tópico por tempo ou tamanho configurado.

Consumidores podem reler eventos enquanto ainda estão retidos.

**Tópicos e Consumidores**

Vários [[Kafka Consumer Groups]] podem ler o mesmo tópico de forma independente.

Isso permite que analytics, auditoria e processamento operacional usem o mesmo fluxo.

---

## Exemplo prático

* pedido-criado
* pagamento-aprovado
* estoque-atualizado

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

Tópicos mal definidos geram acoplamento, excesso de eventos ou dificuldade de governança.

Criar tópico para tudo aumenta fragmentação.

Usar tópico único para tudo aumenta acoplamento.

A escolha precisa seguir domínio, volume, retenção e consumidores.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

**Relação com Domínio**

Um tópico deve representar um fluxo de eventos com significado claro.

Exemplos:

* pedido-criado
* pagamento-aprovado
* usuario-cadastrado

Nomes genéricos como `eventos` dificultam governança.

- [[Apache Kafka]]
- [[Kafka Partitions]]
- [[Kafka Consumer Groups]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
