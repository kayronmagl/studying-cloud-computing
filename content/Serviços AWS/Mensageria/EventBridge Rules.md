EventBridge Rules são regras que selecionam eventos dentro de um [[EventBridge Event Bus]] e os enviam para destinos.

Cada regra usa um [[Event Patterns|event pattern]].

EventBridge Rules aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

EventBridge Rules deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

EventBridge Rules existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Papel**

Rules transformam um barramento genérico em roteamento específico.

**Targets**

Uma regra pode enviar eventos para [[EventBridge Targets]], como [[AWS Lambda|Lambda]], [[Amazon SQS|SQS]], SNS, Step Functions e outros destinos compatíveis.

**Múltiplos Targets**

Uma regra pode enviar eventos para um ou mais targets.

Isso permite que um evento de domínio acione fluxos diferentes sem o produtor conhecer cada consumidor.

**Exemplo na prática**

* PedidoCriado: ↓.
* [[AWS Lambda|Lambda]] de validação
* [[Amazon SQS|SQS]] de pagamento
* Step Functions de workflow

---

## Exemplo prático

* se source: ecommerce.
* e detail-type: PedidoCriado.
* enviar para [[AWS Lambda|Lambda]]

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

Regras muito amplas podem enviar eventos demais.

Regras muito específicas podem deixar de capturar eventos esperados se o contrato mudar.

**Cuidado com Regras Amplas**

Uma regra genérica demais pode capturar eventos indesejados.

Uma regra específica demais pode quebrar quando o contrato do evento muda.

Por isso, padrões de evento devem ser versionados e documentados.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[EventBridge Event Bus]]
- [[Event Patterns]]
- [[EventBridge Targets]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
