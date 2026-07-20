Target Groups são grupos de destinos que recebem tráfego de load balancers.

Eles são usados por [[Application Load Balancer]], [[Network Load Balancer]] e outros mecanismos de balanceamento.

---

## Visão geral

Target Groups ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Destinos

Targets podem ser:

* instâncias [[Amazon EC2]];
* endereços IP;
* containers;
* funções Lambda, em alguns cenários.

---

## Health Checks

Cada target group possui [[Health Checks]].

O load balancer usa esses checks para decidir se o target deve receber tráfego.

---

## Relação com Auto Scaling

[[Auto Scaling Groups]] podem registrar instâncias automaticamente em target groups.

Isso integra escala automática com balanceamento.

---

## Exemplo

Uma aplicação web tem um target group para backend.

O ALB recebe requisições e encaminha para instâncias saudáveis nesse grupo.

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
