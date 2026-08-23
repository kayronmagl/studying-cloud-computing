Comunicação Síncrona e Assíncrona descreve duas formas de interação entre sistemas.

Na comunicação síncrona, o chamador espera resposta. Na assíncrona, o produtor envia trabalho ou evento e não precisa esperar o processamento final.

Comunicação Síncrona e Assíncrona aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Comunicação Síncrona e Assíncrona deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Comunicação Síncrona e Assíncrona existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Síncrona**

Exemplo:

* cliente chama [[APIs|API]]
* [[APIs|API]] consulta banco
* [[APIs|API]] responde cliente

É simples de entender, mas cria dependência direta entre componentes.

Se o destino falha, o chamador sofre.

**Assíncrona**

Exemplo:

* [[APIs|API]] recebe pedido
* [[APIs|API]] coloca mensagem na fila
* worker processa depois

O usuário pode receber resposta rápida enquanto o trabalho pesado ocorre em segundo plano.

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

**Quando Usar Síncrona**

Use quando a resposta imediata é necessária:

* autenticação;
* leitura de dados;
* confirmação direta;
* operações interativas.

**Quando Usar Assíncrona**

Use quando o processamento pode acontecer depois:

* envio de e-mail;
* processamento de imagem;
* geração de relatório;
* integração externa;
* atualização de analytics;
* filas de trabalho.

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

**Relação com AWS**

Na AWS, comunicação assíncrona usa serviços como [[Amazon SQS]], [[Amazon SNS]], [[Amazon EventBridge]], [[Amazon MQ]], [[Amazon MSK]] e [[Amazon Kinesis Data Streams]].
