Amazon MQ é o serviço gerenciado de message broker da AWS para [[Apache ActiveMQ]] e [[RabbitMQ]].

A documentação da AWS descreve o Amazon MQ como serviço gerenciado que cuida da configuração, operação e manutenção de brokers ActiveMQ Classic e RabbitMQ, permitindo migrar brokers existentes sem reescrever código de mensageria.

---

## Visão geral

Amazon MQ aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Por que Usar

Use Amazon MQ quando a aplicação já depende de protocolos, bibliotecas ou padrões tradicionais de broker.

Exemplos:

* JMS;
* AMQP;
* MQTT;
* STOMP;
* OpenWire;
* aplicações legadas;
* sistemas corporativos já integrados com ActiveMQ ou RabbitMQ.

---

## Diferença para SQS

[[Amazon SQS]] é fila cloud-native totalmente gerenciada.

Amazon MQ preserva semântica de broker tradicional.

Se você está criando uma aplicação nova na AWS, SQS/SNS/EventBridge podem ser mais naturais. Se está migrando sistema existente, Amazon MQ pode reduzir reescrita.

---

## Brokers

Um broker é o ambiente que recebe, roteia e entrega mensagens.

Ele pode usar filas, tópicos e protocolos dependendo do motor.

---

## Cuidado

Amazon MQ reduz operação, mas não elimina decisões de broker: tamanho, alta disponibilidade, protocolo, conexões, storage, monitoramento e limites.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

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
