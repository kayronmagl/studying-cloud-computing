Concorrência [[AWS Lambda|Lambda]] é a quantidade de execuções simultâneas de uma função [[AWS Lambda]].

Se mil eventos chegam ao mesmo tempo, a plataforma pode executar muitas instâncias da função em paralelo, respeitando limites da conta, da região e da função.

Concorrência [[AWS Lambda|Lambda]] faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## O que é

Concorrência Lambda deve ser entendido como execução ou integração sem administração direta de servidores. Os servidores continuam existindo, mas a equipe trabalha mais perto de eventos, funções, limites e configuração do serviço.

Serverless não significa ausência de servidores. Significa que o cliente não administra servidores diretamente.

---

## Por que existe

Concorrência é poder de escala, mas também é risco.

Uma função que escala rapidamente pode sobrecarregar:

* [[Amazon RDS]];
* [[APIs|APIs]] externas;
* sistemas legados;
* filas downstream;
* serviços com limite de requisições;
* endpoints de terceiros.

Por isso, controlar concorrência é parte da arquitetura.

---

## Como funciona

**Reserved Concurrency**

Reserved concurrency reserva uma quantidade de concorrência para uma função e também define um teto.

Isso serve para proteger recursos.

Exemplo: uma função que grava no [[Amazon RDS|RDS]] pode ser limitada para não abrir conexões demais.

**Provisioned Concurrency**

Provisioned concurrency mantém ambientes pré-inicializados.

Ela reduz [[Cold Start]], mas aumenta custo porque capacidade fica preparada antecipadamente.

É útil em [[APIs|APIs]] críticas com latência previsível.

---

## Exemplo prático

Uma função processa pedidos.

Sem limite, ela escala para centenas de execuções e derruba o banco.

Com concorrência controlada, a fila cresce temporariamente, mas o banco permanece estável.

Essa troca é arquitetura consciente.

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige [[AWS Identity and Access Management (IAM)|IAM]], logs, retries, DLQ e idempotência.

---

## Diferenças importantes

**Como Diferenciar**

* [[AWS Lambda|Lambda]] executa código por evento.
* [[APIs|API]] Gateway expõe [[APIs|APIs]].
* EventBridge roteia eventos.
* [[Amazon SQS|SQS]] desacopla processamento.
* Step Functions orquestra workflows.

---

## Cuidados

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.

Serverless ainda exige [[AWS Identity and Access Management (IAM)|IAM]], logs, limites, custo, timeout, retries e tratamento de erro.

---

## Relação com outras notas

**Relação com Filas**

Com [[Amazon SQS]], concorrência define quantas mensagens podem ser processadas em paralelo.

Se a fila cresce, aumentar concorrência pode reduzir atraso. Mas se o banco não suportar, o sistema degrada.

A decisão correta envolve [[Amazon CloudWatch]], métricas de erro, duração, fila e saturação de dependências.
