SNS FIFO Topics são tópicos FIFO do [[Amazon SNS]].

Eles oferecem publicação com ordenação e deduplicação em integração com filas FIFO e padrões que exigem consistência de ordem.

---

## Visão geral

SNS FIFO Topics aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Quando Usar

Use quando várias aplicações precisam receber eventos mantendo ordem por grupo.

Exemplos:

* atualizações financeiras;
* status de pedido;
* eventos de estoque;
* alterações sequenciais por entidade.

---

## Relação com SQS FIFO

SNS FIFO pode entregar para [[SQS FIFO Queues]], preservando semântica de ordenação e deduplicação dentro do desenho compatível.

---

## Cuidado

FIFO exige modelagem de grupos de mensagem.

Um único grupo reduz paralelismo. Muitos grupos permitem maior concorrência.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.
