Coreografia é o modelo em que componentes reagem a eventos sem um coordenador central controlando todo o fluxo.

Cada serviço observa eventos relevantes e executa sua parte.

Coreografia faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## O que é

Coreografia deve ser entendido como execução ou integração sem administração direta de servidores. Os servidores continuam existindo, mas a equipe trabalha mais perto de eventos, funções, limites e configuração do serviço.

---

## Por que existe

* baixo acoplamento;
* expansão fácil de consumidores;
* escala independente;
* boa integração com [[Arquitetura Orientada a Eventos]].

---

## Como funciona

O funcionamento normalmente envolve eventos, funções, integrações gerenciadas, permissões e execução sob demanda. Ao estudar Coreografia, acompanhe o evento de entrada, a execução, o estado, a falha e o registro gerado.

---

## Exemplo prático

Um evento `PedidoCriado` é publicado no [[Amazon EventBridge]].

Serviços independentes reagem:

* pagamento inicia cobrança;
* estoque reserva produto;
* analytics registra evento;
* e-mail prepara confirmação.

O produtor do evento não precisa conhecer todos os consumidores.

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige [[AWS Identity and Access Management (IAM)|IAM]], logs, retries, DLQ e idempotência.

---

## Diferenças importantes

**Diferença para Orquestração**

Na [[Orquestração]], um workflow central define a sequência.

Na coreografia, a sequência emerge das reações aos eventos.

---

## Cuidados

**Riscos**

Coreografia pode dificultar rastreamento global do processo.

Sem observabilidade, fica difícil saber onde uma jornada falhou. Por isso, [[Amazon CloudWatch]], logs correlacionados e IDs de evento são importantes.

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.

---

## Relação com outras notas

- [[Arquitetura Orientada a Eventos]]
- [[Amazon EventBridge]]
- [[Amazon S3]]
- [[AWS Lambda]]
- [[Amazon SQS]]
- [[Orquestração]]
- [[Amazon CloudWatch]]
