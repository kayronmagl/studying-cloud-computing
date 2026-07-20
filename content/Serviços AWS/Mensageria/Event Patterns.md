Event Patterns são padrões usados pelo [[Amazon EventBridge]] para selecionar eventos.

Eles definem quais eventos uma regra deve capturar.

---

## Visão geral

Event Patterns aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Exemplo

```json
{
  "source": ["ecommerce"],
  "detail-type": ["PedidoCriado"]
}
```

Esse padrão seleciona eventos de origem `ecommerce` com tipo `PedidoCriado`.

---

## Papel

Event patterns permitem roteamento sem que consumidores recebam todos os eventos.

---

## Relação com Contrato

Se o produtor muda `detail-type` ou estrutura do evento, regras podem parar de funcionar.

---

## Cuidado

Padronize nomes de eventos, campos e versões.

---

## Por que Importam

Sem event patterns, consumidores receberiam eventos demais.

Com padrões, cada regra captura apenas eventos relevantes.

---

## Contrato de Evento

Event patterns dependem da estrutura do evento.

Campos como `source`, `detail-type` e `detail` precisam ser estáveis.

Se produtores mudam nomes ou formatos sem versionamento, regras podem falhar silenciosamente.

---

## Exemplo Prático

Uma regra pode capturar apenas eventos de pagamento aprovado e ignorar pagamentos recusados.

Isso reduz lógica nos consumidores e melhora separação de responsabilidades.

---

## Outro exemplo

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
