SNS Message Filtering permite que assinantes de um tópico SNS recebam apenas mensagens que correspondem a uma política de filtro.

Por padrão, um assinante recebe todas as mensagens do tópico. Com filtro, recebe apenas subconjuntos.

SNS Message Filtering aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

SNS Message Filtering deve ser entendido como comunicação indireta entre partes de uma aplicação. Em vez de um componente depender da resposta imediata de outro, mensagens permitem desacoplar envio, espera, processamento e falha.

---

## Por que existe

Evita criar tópicos demais e reduz processamento desnecessário nos consumidores.

---

## Como funciona

**Base**

Filtros usam atributos ou corpo da mensagem, dependendo da configuração suportada.

---

## Exemplo prático

Um tópico recebe eventos de pedidos.

Assinatura A quer apenas `pagamento=aprovado`.

Assinatura B quer apenas `pagamento=recusado`.

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

Não confunda fila, tópico, evento e stream. Fila distribui mensagens para processamento, tópico publica para assinantes, evento descreve algo ocorrido e stream preserva sequência de registros para consumo contínuo.

---

## Cuidados

Filtros precisam fazer parte do contrato da mensagem.

Se produtores mudam atributos sem controle, consumidores podem parar de receber eventos.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

---

## Relação com outras notas

- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
