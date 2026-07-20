Dead Letter Queue, ou DLQ, é uma fila usada para armazenar mensagens que falharam repetidamente no processamento.

Ela é essencial para resiliência em sistemas assíncronos.

---

## Visão geral

Dead Letter Queue (DLQ) aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Por que Existe

Mensagens podem falhar por:

* payload inválido;
* bug no consumidor;
* timeout;
* permissão ausente;
* dependência fora do ar;
* dado inconsistente.

Sem DLQ, mensagens problemáticas podem ser repetidas indefinidamente ou desaparecer sem diagnóstico.

---

## Funcionamento

* fila principal: ↓.
* consumidor tenta processar: ↓.
* falha repetida: ↓.
* mensagem vai para DLQ


---

## Uso com SQS

No [[Amazon SQS]], uma fila pode enviar mensagens para uma DLQ após exceder um número máximo de recebimentos.

---

## Uso com SNS e Lambda

DLQs também aparecem em integrações com [[Amazon SNS]] e [[AWS Lambda]], dependendo do padrão de entrega e falha.

---

## Boas Práticas

* monitorar DLQ com [[Amazon CloudWatch]];
* criar alarmes;
* preservar payload;
* registrar causa da falha;
* corrigir antes de reprocessar;
* evitar tratar DLQ como lixeira.

DLQ é ferramenta de investigação e recuperação operacional.

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
