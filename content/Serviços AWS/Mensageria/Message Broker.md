Message Broker é um intermediário que recebe mensagens de produtores e entrega a consumidores.

Ele pode oferecer filas, tópicos, roteamento, confirmações, persistência, protocolos e políticas de entrega.

Message Broker aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Message Broker deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

---

## Por que existe

Message Broker existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Papel**

O broker desacopla componentes.

Produtores não precisam conhecer diretamente consumidores.

Consumidores podem processar mensagens no seu ritmo.

---

## Exemplo prático

Na AWS, [[Amazon MQ]] é o serviço de broker gerenciado para [[Apache ActiveMQ]] e [[RabbitMQ]].

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Diferença para Serviços Cloud-Native**

[[Amazon SQS]] e [[Amazon SNS]] oferecem mensageria gerenciada com modelo próprio.

Amazon MQ é mais próximo de brokers tradicionais usados fora da nuvem.

**Quando Usar**

Use broker quando a aplicação exige protocolo ou semântica específica, ou quando migrar sistemas existentes sem reescrever mensageria.

---

## Cuidados

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

---

## Relação com outras notas

- [[Amazon MQ]]
- [[Apache ActiveMQ]]
- [[RabbitMQ]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
