SNS Topics são canais lógicos do [[Amazon SNS]] onde mensagens são publicadas.

Assinantes recebem mensagens publicadas no tópico.

SNS Topics aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

SNS Topics deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

SNS Topics existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Função**

Um tópico representa um assunto ou fluxo de notificação.

Exemplo:

* PedidoCriado
* PagamentoAprovado
* AlertaOperacional

**Assinantes**

Assinantes podem ser:

* [[Amazon SQS]];
* [[AWS Lambda]];
* endpoints HTTP/S;
* e-mail;
* SMS;
* outros destinos compatíveis.

**Semântica**

Um tópico deve representar um assunto claro.

Exemplos:

* PedidoCriado
* PagamentoAprovado
* AlertaCritico

Isso ajuda consumidores a entenderem o significado da mensagem.

**Políticas**

Tópicos podem ter políticas de acesso.

Essas políticas controlam quem pode publicar e quem pode assinar.

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

Tópicos muito genéricos dificultam filtro e governança.

Prefira tópicos com semântica clara.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

**Relação com Fanout**

Um tópico com vários assinantes implementa [[Fanout]].

**Relação com [[Amazon SQS|SQS]]**

Um padrão comum é tópico SNS entregando mensagens para múltiplas filas [[Amazon SQS|SQS]].

Isso combina pub/sub com buffer e reprocessamento.
