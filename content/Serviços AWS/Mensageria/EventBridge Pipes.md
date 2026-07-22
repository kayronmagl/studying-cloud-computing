EventBridge Pipes conectam fontes de eventos a destinos com filtragem, enriquecimento e transformação.

Eles simplificam integrações ponto a ponto sem escrever código intermediário.


EventBridge Pipes aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Modelo

* source: ↓.
* filter: ↓.
* enrichment opcional: ↓.
* target


---

## Fontes e Destinos

Pipes podem conectar fontes como filas, streams e outros recursos a destinos compatíveis.

---

## Uso

* filtrar mensagens antes de processar;
* enriquecer evento;
* conectar fila a workflow;
* reduzir código de cola;
* padronizar integração.

---

## Diferença para Rules

Rules trabalham dentro de event buses.

Pipes conectam diretamente uma source a um target com processamento intermediário.

---

## Cuidado

Pipes facilitam integração, mas ainda precisam de observabilidade, tratamento de erro e permissões corretas.

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
