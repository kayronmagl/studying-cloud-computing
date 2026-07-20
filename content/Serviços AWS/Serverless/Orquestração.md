Orquestração é o modelo em que um componente central coordena as etapas de um processo.

Em serverless, [[AWS Step Functions]] é o principal serviço de orquestração. Ele define a ordem, condições, retries, paralelismo e tratamento de erro de um workflow.

---

## Visão geral

Orquestração faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## Exemplo

Um pedido pode seguir:

1. validar dados;
2. reservar estoque;
3. processar pagamento;
4. emitir nota;
5. enviar e-mail.

O orquestrador sabe qual etapa vem depois e o que fazer em caso de falha.

---

## Vantagens

* fluxo explícito;
* visualização clara;
* tratamento de erro centralizado;
* retries configuráveis;
* auditoria;
* melhor rastreabilidade.

---

## Diferença para Coreografia

Na [[Coreografia]], não há coordenador central. Cada serviço reage a eventos.

Orquestração é mais explícita. Coreografia é mais descentralizada.

---

## Exemplo Prático

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige IAM, logs, retries, DLQ e idempotência.

---

## Cuidados importantes

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.
