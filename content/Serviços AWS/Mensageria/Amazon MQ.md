Amazon MQ é o serviço gerenciado de message broker da AWS para [[Apache ActiveMQ]] e [[RabbitMQ]].

A documentação da AWS descreve o Amazon MQ como serviço gerenciado que cuida da configuração, operação e manutenção de brokers ActiveMQ Classic e RabbitMQ, permitindo migrar brokers existentes sem reescrever código de mensageria.

Amazon MQ aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Amazon MQ deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

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

## Como funciona

**Brokers**

Um broker é o ambiente que recebe, roteia e entrega mensagens.

Ele pode usar filas, tópicos e protocolos dependendo do motor.

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Diferença para [[Amazon SQS|SQS]]**

[[Amazon SQS]] é fila cloud-native totalmente gerenciada.

Amazon MQ preserva semântica de broker tradicional.

Se você está criando uma aplicação nova na AWS, [[Amazon SQS|SQS]]/SNS/EventBridge podem ser mais naturais. Se está migrando sistema existente, Amazon MQ pode reduzir reescrita.

**Como Diferenciar**

* [[Amazon SQS|SQS]] é fila.
* SNS é pub/sub.
* EventBridge é barramento de eventos.
* MQ é broker gerenciado.
* MSK é Kafka gerenciado.
* Kinesis é streaming.

---

## Cuidados

Amazon MQ reduz operação, mas não elimina decisões de broker: tamanho, alta disponibilidade, protocolo, conexões, storage, monitoramento e limites.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Apache ActiveMQ]]
- [[RabbitMQ]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
