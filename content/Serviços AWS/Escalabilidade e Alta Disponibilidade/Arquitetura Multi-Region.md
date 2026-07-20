Arquitetura Multi-Region distribui componentes entre múltiplas [[Regions (Regiões)|regiões]] AWS.

É usada para recuperação de desastre regional, baixa latência global, requisitos regulatórios ou sistemas extremamente críticos.

---

## Visão geral

Arquitetura Multi-Region ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Diferença para Multi-AZ

[[Arquitetura Multi-AZ]] distribui recursos entre zonas dentro de uma região.

Multi-Region distribui recursos entre regiões diferentes.

---

## Benefícios

* tolerância a falhas regionais;
* menor latência para usuários globais;
* residência de dados;
* continuidade de negócio;
* estratégia avançada de disaster recovery.

---

## Desafios

* replicação de dados;
* consistência;
* DNS;
* failover;
* custo;
* observabilidade;
* operação;
* deploy;
* segurança;
* testes.

---

## Serviços Relacionados

* [[Amazon Route 53]];
* [[Route 53 Health Checks]];
* [[Failover Routing]];
* [[Amazon S3]] replication;
* bancos com replicação global quando aplicável;
* [[Amazon CloudWatch]];
* [[AWS CloudTrail]].

---

## Cuidado

Multi-Region é poderoso, mas complexo.

Não deve ser usado apenas por parecer sofisticado. Deve responder a requisitos reais de RTO, RPO, latência ou conformidade.

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
