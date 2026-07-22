Message Broker é um intermediário que recebe mensagens de produtores e entrega a consumidores.

Ele pode oferecer filas, tópicos, roteamento, confirmações, persistência, protocolos e políticas de entrega.


Message Broker aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Papel

O broker desacopla componentes.

Produtores não precisam conhecer diretamente consumidores.

Consumidores podem processar mensagens no seu ritmo.

---

## Exemplos

Na AWS, [[Amazon MQ]] é o serviço de broker gerenciado para [[Apache ActiveMQ]] e [[RabbitMQ]].

---

## Diferença para Serviços Cloud-Native

[[Amazon SQS]] e [[Amazon SNS]] oferecem mensageria gerenciada com modelo próprio.

Amazon MQ é mais próximo de brokers tradicionais usados fora da nuvem.

---

## Quando Usar

Use broker quando a aplicação exige protocolo ou semântica específica, ou quando migrar sistemas existentes sem reescrever mensageria.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.
