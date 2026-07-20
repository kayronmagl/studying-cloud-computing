Tolerância a Falhas é a capacidade de um sistema continuar funcionando mesmo quando uma parte falha.

Não significa que o sistema nunca falha. Significa que ele foi desenhado para absorver falhas sem interrupção total.

---

## Visão geral

Tolerância a Falhas ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Estratégias

* redundância;
* múltiplas [[Availability Zones (AZ)]];
* load balancing;
* replicação;
* filas;
* health checks;
* retry;
* timeout;
* circuit breaker;
* failover.

---

## Exemplo AWS

Uma aplicação web executa instâncias em duas AZs.

Se uma instância falha, o [[Elastic Load Balancing]] para de enviar tráfego para ela. O [[Amazon EC2 Auto Scaling]] cria uma substituta.

---

## Relação com SPOF

Tolerância a falhas reduz [[Single Points of Failure (SPOF)]].

Qualquer componente único e indispensável precisa ser analisado como risco.

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
