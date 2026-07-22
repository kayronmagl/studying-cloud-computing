Kafka Topics são categorias lógicas de eventos no [[Apache Kafka]].

Produtores escrevem eventos em tópicos. Consumidores leem eventos desses tópicos.


Kafka Topics aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Exemplo

* pedido-criado
* pagamento-aprovado
* estoque-atualizado


---

## Partições

Tópicos são divididos em [[Kafka Partitions]].

Partições permitem paralelismo e ordenação dentro de cada partição.

---

## Retenção

Eventos permanecem no tópico por tempo ou tamanho configurado.

Consumidores podem reler eventos enquanto ainda estão retidos.

---

## Cuidado

Tópicos mal definidos geram acoplamento, excesso de eventos ou dificuldade de governança.

---

## Relação com Domínio

Um tópico deve representar um fluxo de eventos com significado claro.

Exemplos:


* pedido-criado
* pagamento-aprovado
* usuario-cadastrado


Nomes genéricos como `eventos` dificultam governança.

---

## Tópicos e Consumidores

Vários [[Kafka Consumer Groups]] podem ler o mesmo tópico de forma independente.

Isso permite que analytics, auditoria e processamento operacional usem o mesmo fluxo.

---

## Cuidado na prática

Criar tópico para tudo aumenta fragmentação.

Usar tópico único para tudo aumenta acoplamento.

A escolha precisa seguir domínio, volume, retenção e consumidores.

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
