EventBridge Rules são regras que selecionam eventos dentro de um [[EventBridge Event Bus]] e os enviam para destinos.

Cada regra usa um [[Event Patterns|event pattern]].

---

## Visão geral

EventBridge Rules aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Exemplo

* se source: ecommerce.
* e detail-type: PedidoCriado.
* enviar para Lambda


---

## Papel

Rules transformam um barramento genérico em roteamento específico.

---

## Targets

Uma regra pode enviar eventos para [[EventBridge Targets]], como Lambda, SQS, SNS, Step Functions e outros destinos compatíveis.

---

## Cuidado

Regras muito amplas podem enviar eventos demais.

Regras muito específicas podem deixar de capturar eventos esperados se o contrato mudar.

---

## Múltiplos Targets

Uma regra pode enviar eventos para um ou mais targets.

Isso permite que um evento de domínio acione fluxos diferentes sem o produtor conhecer cada consumidor.

---

## Exemplo na prática

* PedidoCriado: ↓.
* Lambda de validação
* SQS de pagamento
* Step Functions de workflow


---

## Cuidado com Regras Amplas

Uma regra genérica demais pode capturar eventos indesejados.

Uma regra específica demais pode quebrar quando o contrato do evento muda.

Por isso, padrões de evento devem ser versionados e documentados.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

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
