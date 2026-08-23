Long Polling é uma técnica do [[Amazon SQS]] para reduzir respostas vazias ao consultar uma fila.

Em vez de responder imediatamente quando não há mensagens, o [[Amazon SQS|SQS]] pode esperar por um curto período até uma mensagem chegar.

Long Polling aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Long Polling deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Sem long polling, consumidores podem fazer muitas chamadas vazias.

Isso aumenta custo e desperdício.

* menos chamadas vazias;
* menor custo;
* melhor eficiência;
* menor polling agressivo.

---

## Como funciona

**Funcionamento**

O consumidor chama `ReceiveMessage` com tempo de espera.

Se uma mensagem chegar durante a janela, o [[Amazon SQS|SQS]] responde com ela.

Se não chegar, responde vazio ao final da espera.

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

Long polling não substitui escala de consumidores.

Se a fila cresce, é preciso aumentar capacidade de consumo.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
