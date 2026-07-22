Comunicação Síncrona e Assíncrona descreve duas formas de interação entre sistemas.

Na comunicação síncrona, o chamador espera resposta. Na assíncrona, o produtor envia trabalho ou evento e não precisa esperar o processamento final.


Comunicação Síncrona e Assíncrona aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Síncrona

Exemplo:


* cliente chama API
* API consulta banco
* API responde cliente


É simples de entender, mas cria dependência direta entre componentes.

Se o destino falha, o chamador sofre.

---

## Assíncrona

Exemplo:


* API recebe pedido
* API coloca mensagem na fila
* worker processa depois


O usuário pode receber resposta rápida enquanto o trabalho pesado ocorre em segundo plano.

---

## Quando Usar Síncrona

Use quando a resposta imediata é necessária:

* autenticação;
* leitura de dados;
* confirmação direta;
* operações interativas.

---

## Quando Usar Assíncrona

Use quando o processamento pode acontecer depois:

* envio de e-mail;
* processamento de imagem;
* geração de relatório;
* integração externa;
* atualização de analytics;
* filas de trabalho.

---

## Relação com AWS

Na AWS, comunicação assíncrona usa serviços como [[Amazon SQS]], [[Amazon SNS]], [[Amazon EventBridge]], [[Amazon MQ]], [[Amazon MSK]] e [[Amazon Kinesis Data Streams]].

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
