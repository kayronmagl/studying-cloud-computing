Timeouts são limites de tempo definidos para chamadas entre sistemas.

Eles impedem que uma aplicação espere indefinidamente por uma dependência lenta ou indisponível.


Timeouts ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Por que Importam

Sem timeout, uma dependência travada pode prender threads, conexões, memória e recursos.

Isso pode causar falha em cascata.

---

## Exemplo

Uma aplicação chama API externa de pagamento.

Se a API não responde em 3 segundos, a aplicação interrompe a espera e trata o erro.

---

## Relação com Resiliência

Timeouts são base para [[Retries com Backoff Exponencial]] e [[Circuit Breaker]].

Sem timeout, retry também pode ficar ruim, porque cada tentativa demora demais.

---

## Cuidado

Timeout curto demais gera falhas desnecessárias.

Timeout longo demais degrada experiência e consome recursos.

---

## Exemplo Prático

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Cuidados importantes

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

---

## Como entender isso

Este conceito pertence ao módulo de escalabilidade e alta disponibilidade.

## Ponto central

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

## Como Diferenciar

* CloudWatch observa.
* Auto Scaling ajusta capacidade.
* ELB distribui tráfego.
* Health checks removem destinos ruins.
* Multi-AZ reduz falha zonal.
* RTO e RPO guiam recuperação.

## Cuidado importante

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.
