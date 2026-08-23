Backpressure é a pressão de retorno que ocorre quando consumidores não conseguem acompanhar o ritmo dos produtores.

Em sistemas de mensageria, isso aparece como crescimento de fila, aumento de lag ou atraso no processamento.

Backpressure aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Backpressure deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

---

## Por que existe

Backpressure existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Onde Aparece**

* [[Amazon SQS]]: tamanho e idade da fila aumentam.
* [[Amazon MSK]]: consumer lag aumenta.
* [[Amazon Kinesis Data Streams]]: consumidores ficam atrasados.
* [[Amazon Data Firehose]]: buffers e entrega podem atrasar.

**Como Lidar**

* aumentar consumidores;
* escalar workers;
* aplicar rate limiting;
* usar filas;
* ajustar shards/partições;
* otimizar processamento;
* aplicar backoff;
* separar fluxos críticos.

---

## Exemplo prático

Uma [[APIs|API]] publica mil mensagens por segundo.

Os consumidores processam apenas cem por segundo.

O backlog cresce.

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

Não confunda fila, tópico, evento e stream. Fila distribui mensagens para processamento, tópico publica para assinantes, evento descreve algo ocorrido e stream preserva sequência de registros para consumo contínuo.

---

## Cuidados

Backpressure ignorado vira indisponibilidade, perda de dados, custo ou falha em cascata.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

---

## Relação com outras notas

- [[Amazon SQS]]
- [[Amazon MSK]]
- [[Amazon Kinesis Data Streams]]
- [[Amazon Data Firehose]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
