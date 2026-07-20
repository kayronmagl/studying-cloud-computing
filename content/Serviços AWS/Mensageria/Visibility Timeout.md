Visibility Timeout é o período em que uma mensagem recebida do [[Amazon SQS]] fica invisível para outros consumidores.

Ele começa quando a mensagem é entregue a um consumidor.

---

## Visão geral

Visibility Timeout aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Como Funciona

* consumidor recebe mensagem: ↓.
* mensagem fica invisível: ↓.
* consumidor processa: ↓.
* consumidor deleta mensagem


Se o consumidor não deletar a mensagem antes do timeout expirar, ela volta a aparecer na fila.

---

## Por que Importa

Visibility Timeout evita que vários consumidores processem a mesma mensagem ao mesmo tempo.

Mas se for curto demais, uma mensagem ainda em processamento pode reaparecer.

Se for longo demais, falhas demoram a ser reprocessadas.

---

## Exemplo

Se processamento costuma levar 2 minutos, um visibility timeout de 30 segundos pode ser ruim.

A mensagem pode reaparecer enquanto ainda está sendo processada.

---

## Relação com DLQ

Mensagens que falham repetidamente podem ir para [[Dead Letter Queue (DLQ)]], dependendo da configuração de redrive.

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
