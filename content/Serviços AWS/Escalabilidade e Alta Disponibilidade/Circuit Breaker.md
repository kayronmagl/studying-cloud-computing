Circuit Breaker é um padrão de resiliência que interrompe chamadas para uma dependência quando ela está falhando repetidamente.

Ele evita que uma falha externa derrube o sistema chamador.

Circuit Breaker ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Como um disjuntor elétrico, o circuito abre quando há falhas demais.

Enquanto aberto, novas chamadas são bloqueadas ou respondidas rapidamente com fallback.

Depois de um tempo, o sistema testa se a dependência voltou.

Circuit Breaker pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Circuit Breaker existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Estados**

* fechado;
* aberto;
* meio aberto.

---

## Exemplo prático

Uma aplicação chama serviço de pagamento.

Se o serviço falha muitas vezes, o circuit breaker abre. A aplicação para de insistir temporariamente e evita saturar threads e conexões.

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Diferenças importantes

**Como Diferenciar**

* CloudWatch observa.
* Auto Scaling ajusta capacidade.
* ELB distribui tráfego.
* Health checks removem destinos ruins.
* Multi-AZ reduz falha zonal.
* RTO e RPO guiam recuperação.

---

## Cuidados

Circuit breaker precisa de métricas, thresholds e fallback bem definidos.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com AWS**

Circuit breaker é padrão de aplicação, não um serviço único.

Ele complementa [[Elastic Load Balancing]], [[Health Checks]], [[Amazon CloudWatch]] e retries.
