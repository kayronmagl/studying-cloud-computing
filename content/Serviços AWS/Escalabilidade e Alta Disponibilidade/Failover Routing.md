Failover Routing é uma política de roteamento do [[Amazon Route 53]] usada para direcionar tráfego para um recurso secundário quando o primário falha.


Failover Routing ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Como Funciona

A configuração possui um destino primário e um destino secundário.

O Route 53 usa [[Route 53 Health Checks]] para avaliar saúde do primário.

Se o primário não está saudável, o secundário passa a receber tráfego.

---

## Uso

* recuperação de desastre;
* arquiteturas multi-region;
* ambientes ativo-passivo;
* failover de endpoints públicos;
* continuidade de aplicação.

---

## Relação com RTO

Failover routing pode ajudar a reduzir [[Recovery Time Objective (RTO)]], mas não resolve tudo sozinho.

A aplicação secundária precisa estar pronta, os dados precisam existir e dependências precisam funcionar.

---

## Cuidado

DNS caching pode atrasar mudança.

Além disso, failover de tráfego sem replicação de dados pode levar usuários para ambiente vazio ou desatualizado.

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
