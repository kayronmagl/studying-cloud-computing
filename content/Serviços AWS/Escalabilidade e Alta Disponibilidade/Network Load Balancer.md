Network Load Balancer, ou NLB, é um tipo de load balancer da AWS voltado a alto desempenho em camada de transporte.

Ele opera principalmente com tráfego TCP, UDP e TLS.


Network Load Balancer ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Quando Usar

Use NLB quando precisa de:

* baixa latência;
* alto throughput;
* tráfego TCP/UDP;
* preservação de IP de origem em certos cenários;
* workloads de rede intensivos.

---

## Diferença para ALB

[[Application Load Balancer]] entende HTTP/HTTPS e roteia por camada 7.

Network Load Balancer atua em camada 4, com foco em performance e conexões.

---

## Target Groups

NLB também usa [[Target Groups]] e [[Health Checks]].

---

## Cuidado

NLB não fornece as mesmas regras de roteamento HTTP avançadas do ALB.

A escolha depende do protocolo e do tipo de aplicação.

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
