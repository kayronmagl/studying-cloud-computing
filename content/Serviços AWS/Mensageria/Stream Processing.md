Stream Processing é o processamento de dados em fluxo contínuo.

Em vez de processar arquivos em lote, a aplicação processa eventos conforme eles chegam.


Stream Processing aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Uso

* agregações em tempo real;
* detecção de fraude;
* alertas;
* métricas;
* enriquecimento de eventos;
* janelas temporais;
* transformação de streams.

---

## AWS

Na AWS, pode usar:

* [[Amazon Kinesis Data Streams]];
* [[Amazon MSK]];
* [[Amazon Managed Service for Apache Flink]];
* [[AWS Lambda]] em certos cenários.

---

## Diferença para Batch

Batch processa dados acumulados.

Stream processing processa continuamente.

---

## Cuidado

Stream processing exige controle de estado, janelas, atraso, duplicidade e tolerância a falhas.

---

## Janelas

Processamento de stream frequentemente usa janelas temporais.

Exemplo:


* contar eventos por minuto
* calcular média dos últimos 5 minutos
* detectar anomalia na última hora


---

## Estado

Muitos processamentos precisam manter estado.

Exemplo: contar eventos por usuário ou acompanhar sequência de ações.

---

## Relação com Flink

[[Amazon Managed Service for Apache Flink]] é adequado para processamento contínuo com estado, janelas e transformações complexas.

---

## Cuidado na prática

Stream processing precisa lidar com atraso, duplicidade, eventos fora de ordem e falhas.

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
