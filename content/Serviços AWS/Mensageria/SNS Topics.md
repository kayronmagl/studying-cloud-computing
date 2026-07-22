SNS Topics são canais lógicos do [[Amazon SNS]] onde mensagens são publicadas.

Assinantes recebem mensagens publicadas no tópico.


SNS Topics aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Função

Um tópico representa um assunto ou fluxo de notificação.

Exemplo:


* PedidoCriado
* PagamentoAprovado
* AlertaOperacional


---

## Assinantes

Assinantes podem ser:

* [[Amazon SQS]];
* [[AWS Lambda]];
* endpoints HTTP/S;
* e-mail;
* SMS;
* outros destinos compatíveis.

---

## Relação com Fanout

Um tópico com vários assinantes implementa [[Fanout]].

---

## Cuidado

Tópicos muito genéricos dificultam filtro e governança.

Prefira tópicos com semântica clara.

---

## Semântica

Um tópico deve representar um assunto claro.

Exemplos:


* PedidoCriado
* PagamentoAprovado
* AlertaCritico


Isso ajuda consumidores a entenderem o significado da mensagem.

---

## Políticas

Tópicos podem ter políticas de acesso.

Essas políticas controlam quem pode publicar e quem pode assinar.

---

## Relação com SQS

Um padrão comum é tópico SNS entregando mensagens para múltiplas filas SQS.

Isso combina pub/sub com buffer e reprocessamento.

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
