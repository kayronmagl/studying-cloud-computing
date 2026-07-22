Métricas do Amazon CloudWatch são séries temporais numéricas que representam comportamento de sistemas, aplicações e serviços AWS.

A documentação da AWS descreve métricas como dados sobre a performance dos sistemas, coletados de serviços AWS ou publicados como métricas customizadas.


Métricas do Amazon CloudWatch ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Exemplos

Métricas comuns incluem:

* CPUUtilization;
* RequestCount;
* Latency;
* 5XXErrorRate;
* FreeStorageSpace;
* ApproximateNumberOfMessagesVisible;
* Duration;
* ConcurrentExecutions.

---

## Namespace

Métricas são agrupadas por namespace.

Exemplo: métricas de EC2 ficam em um namespace diferente das métricas de Lambda ou RDS.

---

## Dimensões

Dimensões identificam recortes da métrica.

Exemplo: CPU de uma instância específica, latência de um load balancer específico ou erros de uma função específica.

---

## Relação com Alarmes

[[Alarmes do Amazon CloudWatch]] observam métricas.

Sem métrica, não há alarme significativo.

---

## Cuidado

Nem toda métrica técnica indica experiência do usuário.

CPU baixa não significa aplicação saudável. Latência e taxa de erro podem ser mais importantes.

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
