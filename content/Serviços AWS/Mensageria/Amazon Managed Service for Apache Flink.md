Amazon Managed Service for Apache Flink é o serviço gerenciado da AWS para executar aplicações Apache Flink.

Ele é usado para processamento de streams em tempo real.


Amazon Managed Service for Apache Flink aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Papel

Flink permite processar eventos continuamente com estado, janelas, agregações e transformações.

---

## Uso

* detecção de anomalias;
* agregações por janela;
* métricas em tempo real;
* enriquecimento;
* processamento de eventos;
* analytics contínuo.

---

## Integrações

Pode consumir dados de fontes como [[Amazon Kinesis Data Streams]] e [[Amazon MSK]], e enviar resultados para outros destinos.

---

## Diferença para Lambda

[[AWS Lambda]] funciona bem para processamento simples e event-driven.

Flink é mais adequado para processamento contínuo, com estado e janelas complexas.

---

## Cuidado

Processamento com estado exige atenção a checkpointing, evolução de aplicação, atraso de eventos e semântica de processamento.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

---

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
