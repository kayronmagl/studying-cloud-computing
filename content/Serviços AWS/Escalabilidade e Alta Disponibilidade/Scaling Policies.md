Scaling Policies são políticas que dizem ao [[Amazon EC2 Auto Scaling]] quando aumentar ou reduzir capacidade.

Elas transformam métricas em ação.

Scaling Policies ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Scaling Policies pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Scaling Policies existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Tipos**

Principais tipos:

* [[Target Tracking Scaling]];
* [[Step Scaling]];
* [[Scheduled Scaling]];
* políticas simples;
* políticas baseadas em métricas customizadas.

**Scale Out e Scale In**

Scale out adiciona capacidade. Scale in remove capacidade.

As duas direções precisam de cuidado.

Remover instâncias cedo demais pode derrubar desempenho.

**Cooldown e Estabilização**

Políticas precisam evitar oscilações rápidas.

Se a aplicação escala para cima e para baixo a cada minuto, pode haver instabilidade.

---

## Exemplo prático

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

A métrica escolhida precisa representar demanda real.

CPU nem sempre é a melhor métrica. Para filas, tamanho da fila pode ser melhor. Para [[APIs|APIs]], latência ou requisições podem ser mais úteis.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

- [[Amazon EC2 Auto Scaling]]
- [[Target Tracking Scaling]]
- [[Step Scaling]]
- [[Scheduled Scaling]]
- [[Availability Zones (AZ)]]
- [[Application Load Balancer]]
- [[Amazon CloudWatch]]
