Arquitetura Orientada a Eventos é um estilo arquitetural em que componentes produzem, roteiam e consomem eventos.

Um evento representa algo que aconteceu.

Exemplos:

* `PedidoCriado`;
* `PagamentoAprovado`;
* `ArquivoEnviado`;
* `UsuarioCadastrado`.

Arquitetura Orientada a Eventos aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Arquitetura Orientada a Eventos deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

O produtor não precisa conhecer todos os consumidores.

Consumidores reagem a eventos relevantes.

---

## Como funciona

**Papel na AWS**

Na AWS, esse estilo usa serviços como:

* [[Amazon EventBridge]];
* [[Amazon SNS]];
* [[Amazon SQS]];
* [[AWS Lambda]];
* [[AWS Step Functions]];
* [[Amazon Kinesis Data Streams]].

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

**Riscos**

* duplicidade;
* ordem;
* consistência eventual;
* versão de evento;
* observabilidade;
* rastreamento distribuído;
* retries;
* DLQ.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

**Relação com Mensageria**

Mensageria fornece a infraestrutura para transportar eventos e mensagens.

Arquitetura orientada a eventos define como o sistema se organiza ao redor desses eventos.

- [[Amazon EventBridge]]
- [[Amazon SNS]]
- [[Amazon SQS]]
- [[AWS Lambda]]
- [[AWS Step Functions]]
- [[Amazon Kinesis Data Streams]]
- [[Dead Letter Queue (DLQ)]]
