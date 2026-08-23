SNS FIFO Topics são tópicos FIFO do [[Amazon SNS]].

Eles oferecem publicação com ordenação e deduplicação em integração com filas FIFO e padrões que exigem consistência de ordem.

SNS FIFO Topics aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

SNS FIFO Topics deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

---

## Por que existe

SNS FIFO Topics existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

O funcionamento envolve produtores, consumidores, mensagens, eventos, filas, tópicos, retenção, retries e tratamento de falhas. Ao estudar SNS FIFO Topics, observe se a comunicação é síncrona, assíncrona, por fila, por publicação ou por fluxo de eventos.

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Quando Usar**

Use quando várias aplicações precisam receber eventos mantendo ordem por grupo.

Exemplos:

* atualizações financeiras;
* status de pedido;
* eventos de estoque;
* alterações sequenciais por entidade.

---

## Cuidados

FIFO exige modelagem de grupos de mensagem.

Um único grupo reduz paralelismo. Muitos grupos permitem maior concorrência.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

---

## Relação com outras notas

**Relação com [[Amazon SQS|SQS]] FIFO**

SNS FIFO pode entregar para [[SQS FIFO Queues]], preservando semântica de ordenação e deduplicação dentro do desenho compatível.
