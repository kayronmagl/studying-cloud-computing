Target Groups são grupos de destinos que recebem tráfego de load balancers.

Eles são usados por [[Application Load Balancer]], [[Network Load Balancer]] e outros mecanismos de balanceamento.

Target Groups ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Target Groups pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Target Groups existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Destinos**

Targets podem ser:

* instâncias [[Amazon EC2]];
* endereços IP;
* containers;
* funções [[AWS Lambda|Lambda]], em alguns cenários.

**Health Checks**

Cada target group possui [[Health Checks]].

O load balancer usa esses checks para decidir se o target deve receber tráfego.

---

## Exemplo prático

Uma aplicação web tem um target group para backend.

O ALB recebe requisições e encaminha para instâncias saudáveis nesse grupo.

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

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com Auto Scaling**

[[Auto Scaling Groups]] podem registrar instâncias automaticamente em target groups.

Isso integra escala automática com balanceamento.
