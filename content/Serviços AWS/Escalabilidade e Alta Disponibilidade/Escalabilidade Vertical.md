Escalabilidade Vertical significa aumentar a capacidade de um único recurso.

Exemplo: trocar uma instância pequena por uma maior.

---

## Visão geral

Escalabilidade Vertical ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Exemplo AWS

Uma aplicação em [[Amazon EC2]] pode sair de uma instância menor para outra com mais CPU e memória.

Um banco [[Amazon RDS]] pode ter sua classe aumentada para lidar com mais carga.

---

## Vantagens

* simples de entender;
* não exige grande mudança de arquitetura;
* útil para bancos e workloads stateful;
* pode resolver gargalos imediatos.

---

## Limitações

* há limite máximo de máquina;
* pode exigir parada ou manutenção;
* mantém dependência de um único recurso;
* pode aumentar custo rapidamente;
* não melhora disponibilidade por si só.

---

## Comparação

[[Escalabilidade Horizontal]] é preferida quando a aplicação pode ser distribuída entre múltiplas instâncias.

Mas nem todo workload é facilmente horizontal.

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
