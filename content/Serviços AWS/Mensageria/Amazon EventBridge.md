Amazon EventBridge é o serviço de barramento de eventos da AWS.

Ele permite ingerir, filtrar, transformar e entregar eventos entre aplicações, serviços AWS, SaaS e destinos internos.

A documentação da AWS descreve event buses como roteadores que recebem eventos e os entregam a zero ou mais targets, e EventBridge como serviço para ingerir, filtrar, transformar e entregar eventos.

Amazon EventBridge aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Amazon EventBridge é um barramento de eventos.

Ele recebe eventos, aplica regras e envia para destinos.

---

## Por que existe

Amazon EventBridge existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Modelo**

* event source: ↓.
* event bus: ↓.
* rules: ↓.
* targets

**Componentes**

* [[EventBridge Event Bus]];
* [[EventBridge Rules]];
* [[EventBridge Targets]];
* [[EventBridge Pipes]];
* [[EventBridge Scheduler]];
* [[Event Patterns]].

**Componentes na prática**

* Event bus;
* rules;
* event pattern;
* targets;
* scheduler;
* pipes.

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Diferença para SNS**

SNS é pub/sub por tópico.

EventBridge é roteamento de eventos por padrões, fontes, tipos e regras.

**Diferença para [[Amazon SQS|SQS]]**

[[Amazon SQS|SQS]] armazena mensagens até consumo.

EventBridge roteia eventos para destinos.

**Quando Usar**

Use EventBridge para:

* integração entre serviços;
* arquiteturas orientadas a eventos;
* eventos de serviços AWS;
* roteamento por padrão;
* integração SaaS;
* automação;
* workflows.

**Diferença para SNS e [[Amazon SQS|SQS]]**

[[Amazon SQS|SQS]] é fila.

SNS é pub/sub simples por tópico.

EventBridge é roteamento de eventos por padrão, origem e tipo.

**Quando Usar na prática**

* integração entre serviços;
* automação;
* arquitetura orientada a eventos;
* eventos de SaaS;
* workflows assíncronos.

---

## Cuidados

Eventos precisam de contrato.

Campos, versão, semântica e tipos precisam ser estáveis para consumidores.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

EventBridge roteia eventos. Ele não é uma fila tradicional para manter mensagens até consumo manual.

---

## Relação com outras notas

- [[EventBridge Event Bus]]
- [[EventBridge Rules]]
- [[EventBridge Targets]]
- [[EventBridge Pipes]]
- [[EventBridge Scheduler]]
- [[Event Patterns]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
