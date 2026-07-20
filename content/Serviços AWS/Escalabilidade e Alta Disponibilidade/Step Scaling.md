Step Scaling é uma política de escala que ajusta capacidade em degraus conforme a severidade de um alarme.

Quanto maior o desvio, maior pode ser a ação.

---

## Visão geral

Step Scaling ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Exemplo

* CPU > 60%: adicionar 1 instância.
* CPU > 75%: adicionar 2 instâncias.
* CPU > 90%: adicionar 4 instâncias.


---

## Quando Usar

É útil quando a reação precisa variar conforme intensidade do problema.

---

## Relação com CloudWatch

Step Scaling normalmente usa [[Alarmes do Amazon CloudWatch]].

O alarme entra em estado ALARM e a política aplica o ajuste correspondente.

---

## Cuidado

Degraus mal definidos podem escalar demais ou de menos.

É necessário observar comportamento real da aplicação.

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
