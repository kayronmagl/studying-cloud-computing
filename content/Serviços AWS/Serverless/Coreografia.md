Coreografia é o modelo em que componentes reagem a eventos sem um coordenador central controlando todo o fluxo.

Cada serviço observa eventos relevantes e executa sua parte.

---

## Visão geral

Coreografia faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## Exemplo

Um evento `PedidoCriado` é publicado no [[Amazon EventBridge]].

Serviços independentes reagem:

* pagamento inicia cobrança;
* estoque reserva produto;
* analytics registra evento;
* e-mail prepara confirmação.

O produtor do evento não precisa conhecer todos os consumidores.

---

## Vantagens

* baixo acoplamento;
* expansão fácil de consumidores;
* escala independente;
* boa integração com [[Arquitetura Orientada a Eventos]].

---

## Riscos

Coreografia pode dificultar rastreamento global do processo.

Sem observabilidade, fica difícil saber onde uma jornada falhou. Por isso, [[Amazon CloudWatch]], logs correlacionados e IDs de evento são importantes.

---

## Diferença para Orquestração

Na [[Orquestração]], um workflow central define a sequência.

Na coreografia, a sequência emerge das reações aos eventos.

---

## Exemplo Prático

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige IAM, logs, retries, DLQ e idempotência.

---

## Cuidados importantes

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.
