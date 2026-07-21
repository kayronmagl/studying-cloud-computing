Amazon SQS significa Amazon Simple Queue Service.

É o serviço gerenciado de filas da AWS. Ele permite desacoplar produtores e consumidores usando mensagens armazenadas temporariamente.

A documentação da AWS descreve o SQS como serviço que armazena mensagens em infraestrutura redundante; Standard Queues oferecem entrega pelo menos uma vez, enquanto FIFO Queues ajudam a evitar duplicidade dentro da janela de deduplicação e preservam ordem por grupo de mensagens.

---

## Visão geral

Amazon SQS aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Como Funciona

Fluxo:
* produtor envia mensagem: ↓.
* mensagem fica na fila: ↓.
* consumidor recebe mensagem: ↓.
* mensagem fica invisível por um tempo: ↓.
* consumidor processa: ↓.
* consumidor deleta mensagem


Se o consumidor falha e não deleta a mensagem, ela volta a ficar disponível depois do [[Visibility Timeout]].

---

## Tipos

SQS possui:

* [[SQS Standard Queues]];
* [[SQS FIFO Queues]].

---

## Conceitos Importantes

* [[Visibility Timeout]];
* [[Long Polling]];
* [[Message Retention]];
* [[Delay Queues]];
* [[Dead Letter Queue (DLQ)]];
* [[At-Least-Once Delivery]];
* [[Idempotência]].

---

## Relação com Lambda

[[AWS Lambda]] pode consumir mensagens de SQS por [[Event Source Mapping]].

Isso permite que filas acionem processamento serverless.

---

## Quando Usar

Use SQS para:

* filas de trabalho;
* processamento assíncrono;
* desacoplamento;
* retries;
* buffer de picos;
* integração entre microsserviços;
* proteção de consumidores lentos.

---

## Cuidado

SQS Standard pode entregar mensagens mais de uma vez.

Consumidores precisam ser idempotentes.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

## Explicação principal

Amazon SQS é o serviço de filas da AWS.

Ele desacopla produtores e consumidores. O produtor envia mensagem; o consumidor processa depois.

## Como Funciona na prática

A mensagem fica na fila. Quando um consumidor recebe, ela fica invisível por um período chamado Visibility Timeout. Se for processada, o consumidor deleta. Se falhar, ela reaparece.

## Tipos na prática

* Standard Queue: alta escala, entrega pelo menos uma vez.
* FIFO Queue: ordem por grupo e deduplicação.

## Quando Usar na prática

* filas de trabalho;
* processamento assíncrono;
* buffer de picos;
* integração com Lambda;
* reprocessamento com DLQ.

## Cuidado importante

Standard Queue pode entregar mensagem duplicada. Consumidores precisam ser idempotentes.

---

## Pontos que Costumam Gerar Confusão

Quando o cenário envolve enviar e receber mensagens entre componentes distribuídos de aplicações, a resposta é [[Amazon SQS]].

---

## Como entender

SQS é fila.

Um componente envia mensagem. Outro processa depois.

Isso reduz acoplamento e ajuda a absorver picos.

---

## Cuidado importante na prática

SQS não é cache.

SQS não é DNS.

SQS não é migração de dados.

SQS é mensageria por fila.

---

## Comunicação entre componentes

A diferença entre [[Comunicação Síncrona e Assíncrona]] explica por que filas como SQS ajudam a reduzir dependências diretas entre sistemas.

---

## Fila como desacoplamento

[[Filas de Mensagens]] explicam a base do SQS: um componente envia mensagens e outro processa depois, sem ficarem presos um ao outro.

---

## Mensagens entre sistemas

O SQS é uma aplicação prática de [[Mensageria]], porque permite que componentes distribuídos troquem mensagens sem dependerem diretamente um do outro.

---

## Mensageria na AWS

SQS é um dos principais serviços dentro de [[Serviços de Mensageria na AWS]], usado quando componentes precisam trocar mensagens por fila.
