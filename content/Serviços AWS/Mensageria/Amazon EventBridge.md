Amazon EventBridge é o serviço de barramento de eventos da AWS.

Ele permite ingerir, filtrar, transformar e entregar eventos entre aplicações, serviços AWS, SaaS e destinos internos.

A documentação da AWS descreve event buses como roteadores que recebem eventos e os entregam a zero ou mais targets, e EventBridge como serviço para ingerir, filtrar, transformar e entregar eventos.

---

## Visão geral

Amazon EventBridge aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Modelo

* event source: ↓.
* event bus: ↓.
* rules: ↓.
* targets


---

## Componentes

* [[EventBridge Event Bus]];
* [[EventBridge Rules]];
* [[EventBridge Targets]];
* [[EventBridge Pipes]];
* [[EventBridge Scheduler]];
* [[Event Patterns]].

---

## Diferença para SNS

SNS é pub/sub por tópico.

EventBridge é roteamento de eventos por padrões, fontes, tipos e regras.

---

## Diferença para SQS

SQS armazena mensagens até consumo.

EventBridge roteia eventos para destinos.

---

## Quando Usar

Use EventBridge para:

* integração entre serviços;
* arquiteturas orientadas a eventos;
* eventos de serviços AWS;
* roteamento por padrão;
* integração SaaS;
* automação;
* workflows.

---

## Cuidado

Eventos precisam de contrato.

Campos, versão, semântica e tipos precisam ser estáveis para consumidores.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

---

## Explicação principal

Amazon EventBridge é um barramento de eventos.

Ele recebe eventos, aplica regras e envia para destinos.

## Diferença para SNS e SQS

SQS é fila.

SNS é pub/sub simples por tópico.

EventBridge é roteamento de eventos por padrão, origem e tipo.

## Componentes na prática

* Event bus;
* rules;
* event pattern;
* targets;
* scheduler;
* pipes.

## Quando Usar na prática

* integração entre serviços;
* automação;
* arquitetura orientada a eventos;
* eventos de SaaS;
* workflows assíncronos.

## Cuidado importante

EventBridge roteia eventos. Ele não é uma fila tradicional para manter mensagens até consumo manual.
