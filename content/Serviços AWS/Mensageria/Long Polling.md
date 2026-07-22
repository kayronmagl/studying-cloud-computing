Long Polling é uma técnica do [[Amazon SQS]] para reduzir respostas vazias ao consultar uma fila.

Em vez de responder imediatamente quando não há mensagens, o SQS pode esperar por um curto período até uma mensagem chegar.


Long Polling aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Problema que Resolve

Sem long polling, consumidores podem fazer muitas chamadas vazias.

Isso aumenta custo e desperdício.

---

## Funcionamento

O consumidor chama `ReceiveMessage` com tempo de espera.

Se uma mensagem chegar durante a janela, o SQS responde com ela.

Se não chegar, responde vazio ao final da espera.

---

## Benefícios

* menos chamadas vazias;
* menor custo;
* melhor eficiência;
* menor polling agressivo.

---

## Cuidado

Long polling não substitui escala de consumidores.

Se a fila cresce, é preciso aumentar capacidade de consumo.

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
