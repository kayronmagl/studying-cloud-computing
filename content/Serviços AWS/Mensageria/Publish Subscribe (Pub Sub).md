Publish Subscribe, ou Pub/Sub, é um padrão em que produtores publicam mensagens em um tópico e consumidores assinam esse tópico.

O produtor não precisa conhecer os consumidores.

Publish Subscribe (Pub Sub) aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Publish Subscribe (Pub Sub) deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

* desacoplamento;
* múltiplos consumidores;
* fanout;
* extensibilidade;
* integração entre sistemas;
* publicação única com múltiplos efeitos.

---

## Como funciona

**Modelo**

* publisher: ↓.
* topic: ↓.
* subscriber A
* subscriber B
* subscriber C

**AWS**

Na AWS, o serviço clássico de pub/sub é [[Amazon SNS]].

[[Amazon EventBridge]] também trabalha com publicação e roteamento de eventos, mas com semântica mais rica de barramento, regras e padrões de eventos.

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

Pub/sub pode dificultar rastreamento se muitos consumidores reagem ao mesmo evento.

É necessário observabilidade, contratos de mensagem e governança.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Amazon SNS]]
- [[Amazon EventBridge]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
