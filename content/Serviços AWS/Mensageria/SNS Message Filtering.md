SNS Message Filtering permite que assinantes de um tópico SNS recebam apenas mensagens que correspondem a uma política de filtro.

Por padrão, um assinante recebe todas as mensagens do tópico. Com filtro, recebe apenas subconjuntos.


SNS Message Filtering aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Exemplo

Um tópico recebe eventos de pedidos.

Assinatura A quer apenas `pagamento=aprovado`.

Assinatura B quer apenas `pagamento=recusado`.

---

## Benefício

Evita criar tópicos demais e reduz processamento desnecessário nos consumidores.

---

## Base

Filtros usam atributos ou corpo da mensagem, dependendo da configuração suportada.

---

## Cuidado

Filtros precisam fazer parte do contrato da mensagem.

Se produtores mudam atributos sem controle, consumidores podem parar de receber eventos.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.
