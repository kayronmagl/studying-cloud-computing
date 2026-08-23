Recovery Time Objective, ou RTO, é o tempo máximo aceitável para restaurar um sistema após falha.

Ele responde:

* quanto tempo o sistema pode ficar fora do ar?

Recovery Time Objective (RTO) ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Recovery Time Objective (RTO) pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Recovery Time Objective (RTO) existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

O funcionamento depende de métricas, políticas, balanceamento, redundância, health checks, timeouts, retry, failover e capacidade disponível. Ao estudar Recovery Time Objective (RTO), identifique o que detecta mudança, o que reage e o que mantém o serviço utilizável.

---

## Exemplo prático

Se o RTO é de 15 minutos, a arquitetura e o processo operacional precisam permitir recuperação dentro desse tempo.

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Diferenças importantes

**Trade-off**

RTO menor costuma custar mais.

Recuperar em segundos exige mais redundância e automação do que recuperar em horas.

**Como Diferenciar**

* CloudWatch observa.
* Auto Scaling ajusta capacidade.
* ELB distribui tráfego.
* Health checks removem destinos ruins.
* Multi-AZ reduz falha zonal.
* RTO e RPO guiam recuperação.

---

## Cuidados

RTO não deve ser definido sem entendimento de negócio.

Nem todo sistema precisa voltar em segundos. Nem todo sistema pode esperar horas.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com AWS**

RTO influencia decisões como:

* usar múltiplas [[Availability Zones (AZ)]];
* usar [[Multi-AZ]];
* automatizar failover;
* manter ambiente secundário;
* usar [[Amazon Route 53]] com failover;
* adotar [[Arquitetura Multi-Region]].
