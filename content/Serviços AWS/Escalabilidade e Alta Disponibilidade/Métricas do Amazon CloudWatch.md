Métricas do Amazon CloudWatch são séries temporais numéricas que representam comportamento de sistemas, aplicações e serviços AWS.

A documentação da AWS descreve métricas como dados sobre a performance dos sistemas, coletados de serviços AWS ou publicados como métricas customizadas.

Métricas do Amazon CloudWatch ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Métricas do Amazon CloudWatch pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Métricas do Amazon CloudWatch existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Namespace**

Métricas são agrupadas por namespace.

Exemplo: métricas de [[Amazon EC2|EC2]] ficam em um namespace diferente das métricas de [[AWS Lambda|Lambda]] ou [[Amazon RDS|RDS]].

**Dimensões**

Dimensões identificam recortes da métrica.

Exemplo: CPU de uma instância específica, latência de um load balancer específico ou erros de uma função específica.

---

## Exemplo prático

Métricas comuns incluem:

* CPUUtilization;
* RequestCount;
* Latency;
* 5XXErrorRate;
* FreeStorageSpace;
* ApproximateNumberOfMessagesVisible;
* Duration;
* ConcurrentExecutions.

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

Nem toda métrica técnica indica experiência do usuário.

CPU baixa não significa aplicação saudável. Latência e taxa de erro podem ser mais importantes.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com Alarmes**

[[Alarmes do Amazon CloudWatch]] observam métricas.

Sem métrica, não há alarme significativo.
