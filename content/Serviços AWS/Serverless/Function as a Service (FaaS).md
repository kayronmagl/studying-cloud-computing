Function as a Service, ou FaaS, é o modelo serverless no qual a unidade principal de execução é uma função.

Na AWS, o serviço FaaS central é o [[AWS Lambda]]. O desenvolvedor escreve uma função, define runtime, handler, memória, timeout, permissões e gatilhos. A AWS executa essa função quando ela é invocada.

Function as a Service (FaaS) faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## O que é

Function as a Service (FaaS) deve ser entendido como execução ou integração sem administração direta de servidores. Os servidores continuam existindo, mas a equipe trabalha mais perto de eventos, funções, limites e configuração do serviço.

---

## Por que existe

Function as a Service (FaaS) existe para reduzir a administração direta de servidores e aproximar execução de eventos, demanda real e automação. O ganho aparece quando a arquitetura aceita unidades menores, acoplamento controlado e observabilidade.

---

## Como funciona

**Função como Unidade de Execução**

No FaaS, uma função deve representar uma unidade de comportamento.

Exemplos:

* validar um pedido;
* redimensionar uma imagem;
* processar uma mensagem;
* enviar notificação;
* transformar um arquivo;
* publicar um evento;
* consultar um banco.

O objetivo não é quebrar tudo em funções minúsculas sem critério. O objetivo é isolar responsabilidades que fazem sentido dentro do fluxo.

**Como o FaaS Executa**

Um fluxo comum é:

* evento chega: ↓.
* plataforma invoca função: ↓.
* runtime carrega código: ↓.
* handler recebe event/context: ↓.
* função executa lógica: ↓.
* resultado, erro ou novo evento é produzido

Esse modelo é diferente de um servidor web tradicional, que fica permanentemente executando e aguardando requisições.

**Integração com Eventos**

FaaS combina fortemente com [[Arquitetura Orientada a Eventos]].

Uma função pode ser acionada por eventos de serviços diferentes. Isso permite criar fluxos assíncronos e desacoplados.

Exemplo: um upload no [[Amazon S3|S3]] aciona [[AWS Lambda|Lambda]], que publica evento no EventBridge, que inicia workflow no Step Functions.

---

## Exemplo prático

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige [[AWS Identity and Access Management (IAM)|IAM]], logs, retries, DLQ e idempotência.

---

## Diferenças importantes

Não confunda serverless com ausência de infraestrutura. Servidores continuam existindo, mas a administração direta de capacidade, provisionamento e parte da operação fica com o provedor.

---

## Cuidados

**Riscos**

Os principais riscos são:

* excesso de funções pequenas;
* dificuldade de rastrear fluxo;
* permissões mal definidas;
* retries duplicando efeitos;
* ausência de idempotência;
* cold start em [[APIs|APIs]] sensíveis;
* logs ruins;
* acoplamento escondido por eventos.

Por isso, FaaS exige disciplina arquitetural.

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.

---

## Relação com outras notas

**Relação com Estado**

Funções FaaS devem evitar depender de estado local durável.

O ambiente pode ser reutilizado, mas não deve ser tratado como armazenamento confiável.

Estado importante deve ficar em serviços externos, como:

* [[Amazon S3]];
* [[Amazon RDS]];
* [[Amazon DynamoDB]];
* [[Amazon SQS]];
* caches;
* sistemas de eventos.

Essa regra é essencial para escala e resiliência.
