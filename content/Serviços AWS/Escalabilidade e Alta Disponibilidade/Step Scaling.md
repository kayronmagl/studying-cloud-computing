Step Scaling é uma política de escala que ajusta capacidade em degraus conforme a severidade de um alarme.

Quanto maior o desvio, maior pode ser a ação.

Step Scaling ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Step Scaling pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Step Scaling existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

O funcionamento depende de métricas, políticas, balanceamento, redundância, health checks, timeouts, retry, failover e capacidade disponível. Ao estudar Step Scaling, identifique o que detecta mudança, o que reage e o que mantém o serviço utilizável.

---

## Exemplo prático

* CPU > 60%: adicionar 1 instância.
* CPU > 75%: adicionar 2 instâncias.
* CPU > 90%: adicionar 4 instâncias.

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Diferenças importantes

**Quando Usar**

É útil quando a reação precisa variar conforme intensidade do problema.

**Como Diferenciar**

* CloudWatch observa.
* Auto Scaling ajusta capacidade.
* ELB distribui tráfego.
* Health checks removem destinos ruins.
* Multi-AZ reduz falha zonal.
* RTO e RPO guiam recuperação.

---

## Cuidados

Degraus mal definidos podem escalar demais ou de menos.

É necessário observar comportamento real da aplicação.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com CloudWatch**

Step Scaling normalmente usa [[Alarmes do Amazon CloudWatch]].

O alarme entra em estado ALARM e a política aplica o ajuste correspondente.
