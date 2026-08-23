Amazon Managed Service for Apache Flink é o serviço gerenciado da AWS para executar aplicações Apache Flink.

Ele é usado para processamento de streams em tempo real.

Amazon Managed Service for Apache Flink aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Amazon Managed Service for Apache Flink deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Amazon Managed Service for Apache Flink existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Papel**

Flink permite processar eventos continuamente com estado, janelas, agregações e transformações.

**Uso**

* detecção de anomalias;
* agregações por janela;
* métricas em tempo real;
* enriquecimento;
* processamento de eventos;
* analytics contínuo.

**Integrações**

Pode consumir dados de fontes como [[Amazon Kinesis Data Streams]] e [[Amazon MSK]], e enviar resultados para outros destinos.

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Diferença para [[AWS Lambda|Lambda]]**

[[AWS Lambda]] funciona bem para processamento simples e event-driven.

Flink é mais adequado para processamento contínuo, com estado e janelas complexas.

**Como Diferenciar**

* [[Amazon SQS|SQS]] é fila.
* SNS é pub/sub.
* EventBridge é barramento de eventos.
* MQ é broker gerenciado.
* MSK é Kafka gerenciado.
* Kinesis é streaming.

---

## Cuidados

Processamento com estado exige atenção a checkpointing, evolução de aplicação, atraso de eventos e semântica de processamento.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Amazon Kinesis Data Streams]]
- [[Amazon MSK]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
- [[AWS Lambda]]
