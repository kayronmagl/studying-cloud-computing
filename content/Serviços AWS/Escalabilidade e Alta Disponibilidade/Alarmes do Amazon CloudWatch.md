Alarmes do Amazon CloudWatch monitoram métricas e mudam de estado quando uma condição é atingida.

Eles conectam observabilidade a ação.

Alarmes do Amazon CloudWatch ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Alarmes do Amazon CloudWatch pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Alarmes do Amazon CloudWatch existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Estados**

Um alarme pode estar em estados como:

* OK;
* ALARM;
* INSUFFICIENT_DATA.

**Ações**

Alarmes podem:

* enviar notificações;
* acionar políticas de [[Amazon EC2 Auto Scaling]];
* integrar automações;
* indicar incidentes.

---

## Exemplo prático

* se CPU média > 70% por 5 minutos: estado ALARM.
* acionar política de escala

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

Alarmes mal calibrados geram ruído.

Alarmes atrasados podem detectar problema tarde demais. Alarmes sensíveis demais podem gerar flapping.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com Auto Scaling**

Auto Scaling pode usar alarmes para decidir quando aumentar ou reduzir capacidade.

- [[Amazon EC2 Auto Scaling]]
- [[Availability Zones (AZ)]]
- [[Application Load Balancer]]
- [[Amazon CloudWatch]]
