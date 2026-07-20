RabbitMQ é um message broker open source baseado originalmente no protocolo AMQP.

Ele é usado para filas, roteamento, pub/sub e integração entre sistemas.

---

## Visão geral

RabbitMQ aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Relação com AWS

[[Amazon MQ]] pode executar brokers compatíveis com RabbitMQ.

Isso permite migrar workloads existentes para a AWS mantendo bibliotecas e padrões conhecidos.

---

## Características

RabbitMQ trabalha com conceitos como exchanges, queues, bindings e routing keys.

---

## Diferença para SNS/SQS

[[Amazon SNS]] e [[Amazon SQS]] são serviços cloud-native.

RabbitMQ oferece semântica tradicional de broker e pode ser necessário quando a aplicação já depende desse modelo.

---

## Cuidado

RabbitMQ exige cuidado com conexões, filas, mensagens persistentes, acknowledgements, consumo e dimensionamento.

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
