Escalabilidade e Balanceamento de Carga é a combinação entre adicionar/remover capacidade e distribuir tráfego entre recursos saudáveis.

Na AWS, isso normalmente envolve [[Amazon EC2 Auto Scaling]] e [[Elastic Load Balancing]].


Escalabilidade e Balanceamento de Carga ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Como se Integram

O fluxo típico é:


* Amazon CloudWatch observa métricas: ↓.
* Auto Scaling ajusta instâncias: ↓.
* novas instâncias entram no Target Group: ↓.
* Load Balancer distribui tráfego: ↓.
* Health Checks removem destinos ruins


---

## Por que Funciona

Auto Scaling cuida da quantidade de capacidade.

Load Balancing cuida da distribuição de tráfego.

Health Checks cuidam de evitar destinos ruins.

CloudWatch cuida da observabilidade.

---

## Exemplo

Durante pico de tráfego, novas instâncias EC2 são lançadas. Quando passam no health check, entram no target group. O ALB passa a distribuir requisições para elas.

Quando o pico termina, instâncias são removidas de forma controlada.

---

## Cuidado

A aplicação precisa ser preparada para escala horizontal.

Sessões locais, arquivos locais e estado preso na instância dificultam balanceamento.

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
