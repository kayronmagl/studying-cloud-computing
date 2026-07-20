Arquitetura Multi-AZ distribui componentes entre múltiplas [[Availability Zones (AZ)]] dentro da mesma região.

É um dos padrões mais importantes de [[Alta Disponibilidade]] na AWS.

---

## Visão geral

Arquitetura Multi-AZ ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Por que Usar

Uma AZ pode sofrer falha local.

Se toda a aplicação está em uma única AZ, a falha pode derrubar o sistema.

Distribuir recursos entre AZs reduz esse risco.

---

## Exemplo

Uma aplicação web pode usar:

* [[Application Load Balancer]] em sub-redes públicas de duas AZs;
* instâncias EC2 em sub-redes privadas de duas AZs;
* [[Auto Scaling Groups]] distribuídos;
* [[Amazon RDS]] com [[Multi-AZ]];
* [[Amazon CloudWatch]] para alarmes.

---

## Relação com Rede

Multi-AZ depende de [[Redes na AWS]] bem desenhadas.

Subnets precisam existir em múltiplas zonas. Route tables, security groups e load balancers precisam refletir esse desenho.

---

## Cuidado

Multi-AZ não é o mesmo que multi-region.

Se a região inteira falhar, Multi-AZ dentro daquela região pode não bastar.

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
