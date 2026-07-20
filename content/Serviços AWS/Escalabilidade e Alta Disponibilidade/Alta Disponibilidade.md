Alta Disponibilidade é a capacidade de um sistema continuar funcionando mesmo diante de falhas.

Em AWS, alta disponibilidade normalmente significa distribuir componentes entre múltiplas [[Availability Zones (AZ)]], eliminar [[Single Points of Failure (SPOF)]] e automatizar recuperação.

---

## Visão geral

Alta Disponibilidade ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Objetivo

O objetivo não é impedir toda falha.

Falhas acontecem.

O objetivo é impedir que uma falha isolada derrube o serviço inteiro.

---

## Componentes

Alta disponibilidade usa:

* redundância;
* múltiplas AZs;
* health checks;
* load balancers;
* failover;
* replicação;
* backups;
* monitoramento;
* automação;
* bancos Multi-AZ.

---

## Exemplo

Uma aplicação com uma única instância EC2 tem baixa disponibilidade.

Uma aplicação com várias instâncias em múltiplas AZs, atrás de um [[Application Load Balancer]], com [[Auto Scaling Groups]] e banco [[Multi-AZ]], possui disponibilidade maior.

---

## Relação com Resiliência

[[Resiliência]] inclui alta disponibilidade, recuperação, tolerância a falhas e capacidade de adaptação.

Alta disponibilidade é um subconjunto importante da resiliência.

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
