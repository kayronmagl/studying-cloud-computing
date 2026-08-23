Visibility Timeout é o período em que uma mensagem recebida do [[Amazon SQS]] fica invisível para outros consumidores.

Ele começa quando a mensagem é entregue a um consumidor.

Visibility Timeout aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Visibility Timeout deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Visibility Timeout evita que vários consumidores processem a mesma mensagem ao mesmo tempo.

Mas se for curto demais, uma mensagem ainda em processamento pode reaparecer.

Se for longo demais, falhas demoram a ser reprocessadas.

---

## Como funciona

* consumidor recebe mensagem: ↓.
* mensagem fica invisível: ↓.
* consumidor processa: ↓.
* consumidor deleta mensagem

Se o consumidor não deletar a mensagem antes do timeout expirar, ela volta a aparecer na fila.

---

## Exemplo prático

Se processamento costuma levar 2 minutos, um visibility timeout de 30 segundos pode ser ruim.

A mensagem pode reaparecer enquanto ainda está sendo processada.

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

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

**Relação com DLQ**

Mensagens que falham repetidamente podem ir para [[Dead Letter Queue (DLQ)]], dependendo da configuração de redrive.
