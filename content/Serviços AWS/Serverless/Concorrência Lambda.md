Concorrência Lambda é a quantidade de execuções simultâneas de uma função [[AWS Lambda]].

Se mil eventos chegam ao mesmo tempo, a plataforma pode executar muitas instâncias da função em paralelo, respeitando limites da conta, da região e da função.


Concorrência Lambda faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## Por que Importa

Concorrência é poder de escala, mas também é risco.

Uma função que escala rapidamente pode sobrecarregar:

* [[Amazon RDS]];
* APIs externas;
* sistemas legados;
* filas downstream;
* serviços com limite de requisições;
* endpoints de terceiros.

Por isso, controlar concorrência é parte da arquitetura.

---

## Reserved Concurrency

Reserved concurrency reserva uma quantidade de concorrência para uma função e também define um teto.

Isso serve para proteger recursos.

Exemplo: uma função que grava no RDS pode ser limitada para não abrir conexões demais.

---

## Provisioned Concurrency

Provisioned concurrency mantém ambientes pré-inicializados.

Ela reduz [[Cold Start]], mas aumenta custo porque capacidade fica preparada antecipadamente.

É útil em APIs críticas com latência previsível.

---

## Relação com Filas

Com [[Amazon SQS]], concorrência define quantas mensagens podem ser processadas em paralelo.

Se a fila cresce, aumentar concorrência pode reduzir atraso. Mas se o banco não suportar, o sistema degrada.

A decisão correta envolve [[Amazon CloudWatch]], métricas de erro, duração, fila e saturação de dependências.

---

## Exemplo

Uma função processa pedidos.

Sem limite, ela escala para centenas de execuções e derruba o banco.

Com concorrência controlada, a fila cresce temporariamente, mas o banco permanece estável.

Essa troca é arquitetura consciente.

---

## Exemplo Prático

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige IAM, logs, retries, DLQ e idempotência.

---

## Cuidados importantes

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.

## Como entender isso

Este conceito pertence ao modelo serverless.

## Ponto central

Serverless não significa ausência de servidores. Significa que o cliente não administra servidores diretamente.

## Como Diferenciar

* Lambda executa código por evento.
* API Gateway expõe APIs.
* EventBridge roteia eventos.
* SQS desacopla processamento.
* Step Functions orquestra workflows.

## Cuidado importante

Serverless ainda exige IAM, logs, limites, custo, timeout, retries e tratamento de erro.
