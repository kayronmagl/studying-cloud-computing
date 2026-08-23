Mensageria é o uso de mensagens para comunicação entre componentes de software.

Em vez de um componente depender diretamente de outro em tempo real, ele publica uma mensagem em uma fila, tópico, broker, barramento de eventos ou stream.

Mensageria aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Mensageria deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Mensageria existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Papel Arquitetural**

Mensageria permite:

* desacoplamento;
* processamento assíncrono;
* absorção de picos;
* fanout;
* integração entre sistemas;
* buffer entre produtor e consumidor;
* maior tolerância a falhas;
* reprocessamento;
* auditoria de eventos.

**Mensagem**

Uma mensagem normalmente possui:

* corpo;
* atributos;
* identificador;
* timestamp;
* metadados;
* destino lógico;
* informações de roteamento.

**Comunicação Direta vs Mensageria**

Chamada direta:

* A chama B
* A espera B

Mensageria:

* A publica mensagem
* B processa depois

Esse modelo reduz dependência temporal.

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

Mensageria não elimina complexidade.

Ela muda a complexidade para consistência eventual, duplicidade, ordenação, observabilidade e tratamento de erro.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
