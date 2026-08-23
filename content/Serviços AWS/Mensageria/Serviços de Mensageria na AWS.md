Serviços de Mensageria na AWS são serviços usados para comunicação assíncrona, desacoplamento, publicação de eventos, filas, brokers e streaming de dados.

Eles resolvem um problema central de sistemas distribuídos: componentes não devem depender sempre de chamadas diretas, síncronas e frágeis.

Serviços de Mensageria na AWS aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Serviços de Mensageria na AWS deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Serviços de Mensageria na AWS existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Por que Mensageria Existe**

Em um sistema simples, um serviço chama outro diretamente.

Isso funciona até que:

* o destino fique lento;
* o destino fique fora do ar;
* o produtor gere mais trabalho do que o consumidor suporta;
* vários sistemas precisem reagir ao mesmo evento;
* uma tarefa demore demais para responder ao usuário;
* seja necessário processar dados continuamente.

Mensageria cria uma camada intermediária para desacoplar produção e consumo.

**Famílias**

Na AWS, as famílias principais são:

* filas com [[Amazon SQS]];
* pub/sub com [[Amazon SNS]];
* eventos com [[Amazon EventBridge]];
* brokers com [[Amazon MQ]];
* streaming Kafka com [[Amazon MSK]];
* streaming nativo com [[Amazon Kinesis Data Streams]];
* entrega gerenciada com [[Amazon Data Firehose]];
* processamento com [[Amazon Managed Service for Apache Flink]].

**Conceitos Transversais**

Para comparar serviços de mensageria, alguns conceitos precisam ficar claros:

* [[Message Broker]], usado em brokers tradicionais como [[Amazon MQ]];
* [[Ordering and Delivery Semantics]], que define garantias de ordem e entrega;
* [[Backpressure]], que aparece quando consumidores não acompanham produtores.

Esses conceitos ajudam a escolher entre filas, tópicos, event buses, brokers e streams.

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

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

**Relação com Serverless**

Mensageria se conecta fortemente com [[Computação sem Servidor (Serverless)]].

Filas [[Amazon SQS|SQS]] podem acionar [[AWS Lambda]]. Eventos do EventBridge podem iniciar workflows. Tópicos SNS podem distribuir mensagens para múltiplas funções e filas.

**Relação com Resiliência**

Mensageria melhora resiliência porque permite absorver picos, tolerar indisponibilidade temporária, reprocessar falhas e proteger consumidores lentos.

Mas ela também exige cuidado com duplicidade, ordem, retenção, DLQ, idempotência e observabilidade.
