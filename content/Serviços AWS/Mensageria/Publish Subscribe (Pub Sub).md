Publish Subscribe, ou Pub/Sub, é um padrão em que produtores publicam mensagens em um tópico e consumidores assinam esse tópico.

O produtor não precisa conhecer os consumidores.

---

## Visão geral

Publish Subscribe (Pub Sub) aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Modelo

* publisher: ↓.
* topic: ↓.
* subscriber A
* subscriber B
* subscriber C


---

## Vantagens

* desacoplamento;
* múltiplos consumidores;
* fanout;
* extensibilidade;
* integração entre sistemas;
* publicação única com múltiplos efeitos.

---

## AWS

Na AWS, o serviço clássico de pub/sub é [[Amazon SNS]].

[[Amazon EventBridge]] também trabalha com publicação e roteamento de eventos, mas com semântica mais rica de barramento, regras e padrões de eventos.

---

## Cuidado

Pub/sub pode dificultar rastreamento se muitos consumidores reagem ao mesmo evento.

É necessário observabilidade, contratos de mensagem e governança.

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
