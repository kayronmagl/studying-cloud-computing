Event Source Mapping é o recurso que conecta fontes de eventos baseadas em filas ou streams a uma função [[AWS Lambda]].

Ele lê registros da fonte, agrupa em lotes e invoca a função automaticamente.


Event Source Mapping faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## Fontes Comuns

Event Source Mapping é usado com:

* [[Amazon SQS]];
* DynamoDB Streams;
* Kinesis;
* Amazon MSK.

O caso mais didático para começar é SQS.

---

## Como Funciona

O Lambda mantém pollers que leem a fonte.

Quando há mensagens ou registros, ele cria um lote e invoca a função com esse lote no objeto `event`.

Se a função conclui com sucesso, as mensagens podem ser removidas ou os registros avançam.

Se a função falha, entram regras de retry, visibilidade, reprocessamento ou [[Dead Letter Queue (DLQ)]].

---

## Batch Size

Batch size define quantos registros podem ser enviados em uma invocação.

Lotes maiores aumentam throughput, mas podem dificultar tratamento de erro.

Lotes menores facilitam isolamento de falha, mas podem aumentar custo e overhead.

---

## Relação com Concorrência

A escala do Event Source Mapping afeta [[Concorrência Lambda]].

Se muitas mensagens chegam, o Lambda pode aumentar execuções paralelas. Isso melhora processamento, mas pode pressionar bancos e APIs.

---

## Exemplo

Uma fila SQS recebe eventos de pedidos.

O Event Source Mapping lê mensagens em lotes de 10 e invoca uma função Lambda. A função valida pedidos e grava no banco. Mensagens inválidas vão para uma DLQ.

Esse mecanismo é uma ponte entre filas gerenciadas e execução serverless.

---

## Exemplo Prático

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige IAM, logs, retries, DLQ e idempotência.

---

## Cuidados importantes

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.
