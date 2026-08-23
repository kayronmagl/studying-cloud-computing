Auto Scaling Groups, ou ASGs, são coleções de instâncias [[Amazon EC2]] gerenciadas pelo [[Amazon EC2 Auto Scaling]].

O grupo mantém a quantidade de instâncias dentro de limites definidos.

Auto Scaling Groups ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Auto Scaling Groups pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Auto Scaling Groups existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Capacidades**

Um ASG possui:

* capacidade mínima;
* capacidade desejada;
* capacidade máxima.

Exemplo:

* mínimo: 2
* desejado: 4
* máximo: 10

**Launch Template**

O grupo usa [[Launch Templates]] para saber como criar novas instâncias.

O template define AMI, tipo de instância, security groups, user data, [[AWS Identity and Access Management (IAM)|IAM]] role e outros parâmetros.

**Sub-redes**

ASGs normalmente usam múltiplas sub-redes em múltiplas [[Availability Zones (AZ)]], aumentando disponibilidade.

**Integração com Load Balancer**

ASGs podem registrar instâncias em [[Target Groups]] usados por load balancers.

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

A capacidade máxima precisa ser planejada.

Um máximo baixo limita escala. Um máximo alto demais pode aumentar custo se métricas ou alarmes estiverem errados.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

- [[Amazon EC2]]
- [[Amazon EC2 Auto Scaling]]
- [[Launch Templates]]
- [[Availability Zones (AZ)]]
- [[Target Groups]]
- [[Application Load Balancer]]
- [[Amazon CloudWatch]]
