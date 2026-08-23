Cold Start é a latência adicional que ocorre quando uma plataforma serverless precisa preparar um novo ambiente de execução antes de rodar o código.

No [[AWS Lambda]], isso pode acontecer quando a função é invocada pela primeira vez, depois de um período de inatividade ou quando a concorrência aumenta e novos ambientes precisam ser criados.

Cold Start faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## O que é

Cold Start deve ser entendido como execução ou integração sem administração direta de servidores. Os servidores continuam existindo, mas a equipe trabalha mais perto de eventos, funções, limites e configuração do serviço.

---

## Por que existe

Cold Start existe para reduzir a administração direta de servidores e aproximar execução de eventos, demanda real e automação. O ganho aparece quando a arquitetura aceita unidades menores, acoplamento controlado e observabilidade.

---

## Como funciona

**Por que Acontece**

Antes do handler executar, a plataforma pode precisar:

* alocar ambiente;
* carregar runtime;
* baixar ou montar o código;
* inicializar dependências;
* executar código fora do handler;
* preparar extensões;
* configurar rede;
* abrir conexões iniciais.

Esse tempo soma latência à primeira execução daquele ambiente.

**Cold Start vs Warm Start**

No cold start, o ambiente precisa ser preparado.

No warm start, um ambiente já existente é reutilizado.

Warm starts tendem a ser mais rápidos, mas não devem ser usados como garantia de armazenamento durável. Qualquer estado importante precisa ficar em serviços externos, como [[Amazon S3]], [[Amazon RDS]] ou [[Amazon DynamoDB]].

**Impacto**

Cold start importa mais em [[APIs|APIs]] síncronas.

Exemplo: uma função atrás do [[Amazon API Gateway]] pode impactar o tempo de resposta percebido pelo usuário.

Em fluxos assíncronos com [[Amazon SQS]], o impacto costuma ser menor, porque o usuário não está esperando resposta imediata.

**Como Reduzir**

Estratégias:

* diminuir tamanho do pacote;
* reduzir dependências;
* evitar inicialização pesada;
* escolher runtime adequado;
* reutilizar conexões quando possível;
* usar provisioned concurrency em rotas críticas;
* medir duração e init duration no [[Amazon CloudWatch]].

---

## Exemplo prático

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige [[AWS Identity and Access Management (IAM)|IAM]], logs, retries, DLQ e idempotência.

---

## Diferenças importantes

Não confunda serverless com ausência de infraestrutura. Servidores continuam existindo, mas a administração direta de capacidade, provisionamento e parte da operação fica com o provedor.

---

## Cuidados

**Erro Comum**

Tentar eliminar todo cold start sem medir impacto real.

A decisão deve partir de métricas: latência percebida, frequência de invocações, custo e criticidade do endpoint.

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.

---

## Relação com outras notas

- [[AWS Lambda]]
- [[Amazon S3]]
- [[Amazon RDS]]
- [[Amazon DynamoDB]]
- [[Amazon API Gateway]]
- [[Amazon SQS]]
- [[Amazon CloudWatch]]
- [[Amazon EventBridge]]
