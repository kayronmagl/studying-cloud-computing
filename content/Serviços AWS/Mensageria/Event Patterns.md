Event Patterns são padrões usados pelo [[Amazon EventBridge]] para selecionar eventos.

Eles definem quais eventos uma regra deve capturar.

Event Patterns aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

Event Patterns deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

Mensageria desacopla produtores e consumidores.

---

## Por que existe

Event Patterns existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Papel**

Event patterns permitem roteamento sem que consumidores recebam todos os eventos.

**Por que Importam**

Sem event patterns, consumidores receberiam eventos demais.

Com padrões, cada regra captura apenas eventos relevantes.

**Contrato de Evento**

Event patterns dependem da estrutura do evento.

Campos como `source`, `detail-type` e `detail` precisam ser estáveis.

Se produtores mudam nomes ou formatos sem versionamento, regras podem falhar silenciosamente.

---

## Exemplo prático

```json
{
  "source": ["ecommerce"],
  "detail-type": ["PedidoCriado"]
}
```

Esse padrão seleciona eventos de origem `ecommerce` com tipo `PedidoCriado`.

Uma regra pode capturar apenas eventos de pagamento aprovado e ignorar pagamentos recusados.

Isso reduz lógica nos consumidores e melhora separação de responsabilidades.

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

Padronize nomes de eventos, campos e versões.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

Mensageria exige idempotência, retries, DLQ e observabilidade.

---

## Relação com outras notas

**Relação com Contrato**

Se o produtor muda `detail-type` ou estrutura do evento, regras podem parar de funcionar.

- [[Amazon EventBridge]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
