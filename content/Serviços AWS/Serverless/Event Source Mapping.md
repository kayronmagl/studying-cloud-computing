Event Source Mapping é o recurso que conecta fontes de eventos baseadas em filas ou streams a uma função [[AWS Lambda]].

Ele lê registros da fonte, agrupa em lotes e invoca a função automaticamente.

Event Source Mapping faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## O que é

Event Source Mapping deve ser entendido como execução ou integração sem administração direta de servidores. Os servidores continuam existindo, mas a equipe trabalha mais perto de eventos, funções, limites e configuração do serviço.

---

## Por que existe

Event Source Mapping existe para reduzir a administração direta de servidores e aproximar execução de eventos, demanda real e automação. O ganho aparece quando a arquitetura aceita unidades menores, acoplamento controlado e observabilidade.

---

## Como funciona

**Fontes Comuns**

Event Source Mapping é usado com:

* [[Amazon SQS]];
* [[Amazon DynamoDB|DynamoDB]] Streams;
* Kinesis;
* Amazon MSK.

O caso mais didático para começar é [[Amazon SQS|SQS]].

O [[AWS Lambda|Lambda]] mantém pollers que leem a fonte.

Quando há mensagens ou registros, ele cria um lote e invoca a função com esse lote no objeto `event`.

Se a função conclui com sucesso, as mensagens podem ser removidas ou os registros avançam.

Se a função falha, entram regras de retry, visibilidade, reprocessamento ou [[Dead Letter Queue (DLQ)]].

**Batch Size**

Batch size define quantos registros podem ser enviados em uma invocação.

Lotes maiores aumentam throughput, mas podem dificultar tratamento de erro.

Lotes menores facilitam isolamento de falha, mas podem aumentar custo e overhead.

---

## Exemplo prático

Uma fila [[Amazon SQS|SQS]] recebe eventos de pedidos.

O Event Source Mapping lê mensagens em lotes de 10 e invoca uma função [[AWS Lambda|Lambda]]. A função valida pedidos e grava no banco. Mensagens inválidas vão para uma DLQ.

Esse mecanismo é uma ponte entre filas gerenciadas e execução serverless.

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige [[AWS Identity and Access Management (IAM)|IAM]], logs, retries, DLQ e idempotência.

---

## Diferenças importantes

Não confunda serverless com ausência de infraestrutura. Servidores continuam existindo, mas a administração direta de capacidade, provisionamento e parte da operação fica com o provedor.

---

## Cuidados

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.

---

## Relação com outras notas

**Relação com Concorrência**

A escala do Event Source Mapping afeta [[Concorrência Lambda]].

Se muitas mensagens chegam, o [[AWS Lambda|Lambda]] pode aumentar execuções paralelas. Isso melhora processamento, mas pode pressionar bancos e [[APIs|APIs]].
