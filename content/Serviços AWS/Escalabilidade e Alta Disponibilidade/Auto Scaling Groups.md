Auto Scaling Groups, ou ASGs, são coleções de instâncias [[Amazon EC2]] gerenciadas pelo [[Amazon EC2 Auto Scaling]].

O grupo mantém a quantidade de instâncias dentro de limites definidos.

---

## Visão geral

Auto Scaling Groups ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Capacidades

Um ASG possui:

* capacidade mínima;
* capacidade desejada;
* capacidade máxima.

Exemplo:


* mínimo: 2
* desejado: 4
* máximo: 10


---

## Launch Template

O grupo usa [[Launch Templates]] para saber como criar novas instâncias.

O template define AMI, tipo de instância, security groups, user data, IAM role e outros parâmetros.

---

## Sub-redes

ASGs normalmente usam múltiplas sub-redes em múltiplas [[Availability Zones (AZ)]], aumentando disponibilidade.

---

## Integração com Load Balancer

ASGs podem registrar instâncias em [[Target Groups]] usados por load balancers.

---

## Cuidado

A capacidade máxima precisa ser planejada.

Um máximo baixo limita escala. Um máximo alto demais pode aumentar custo se métricas ou alarmes estiverem errados.

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
