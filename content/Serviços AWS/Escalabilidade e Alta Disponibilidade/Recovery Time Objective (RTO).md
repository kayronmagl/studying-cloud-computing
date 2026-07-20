Recovery Time Objective, ou RTO, é o tempo máximo aceitável para restaurar um sistema após falha.

Ele responde:


* quanto tempo o sistema pode ficar fora do ar?


---

## Visão geral

Recovery Time Objective (RTO) ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Exemplo

Se o RTO é de 15 minutos, a arquitetura e o processo operacional precisam permitir recuperação dentro desse tempo.

---

## Relação com AWS

RTO influencia decisões como:

* usar múltiplas [[Availability Zones (AZ)]];
* usar [[Multi-AZ]];
* automatizar failover;
* manter ambiente secundário;
* usar [[Amazon Route 53]] com failover;
* adotar [[Arquitetura Multi-Region]].

---

## Trade-off

RTO menor costuma custar mais.

Recuperar em segundos exige mais redundância e automação do que recuperar em horas.

---

## Cuidado

RTO não deve ser definido sem entendimento de negócio.

Nem todo sistema precisa voltar em segundos. Nem todo sistema pode esperar horas.

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
