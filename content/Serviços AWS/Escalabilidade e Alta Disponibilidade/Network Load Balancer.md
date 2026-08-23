Network Load Balancer, ou NLB, é um tipo de load balancer da AWS voltado a alto desempenho em camada de transporte.

Ele opera principalmente com tráfego TCP, UDP e TLS.

Network Load Balancer ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Network Load Balancer pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Network Load Balancer existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Target Groups**

NLB também usa [[Target Groups]] e [[Health Checks]].

---

## Exemplo prático

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Diferenças importantes

**Quando Usar**

Use NLB quando precisa de:

* baixa latência;
* alto throughput;
* tráfego TCP/UDP;
* preservação de IP de origem em certos cenários;
* workloads de rede intensivos.

**Diferença para ALB**

[[Application Load Balancer]] entende HTTP/HTTPS e roteia por camada 7.

Network Load Balancer atua em camada 4, com foco em performance e conexões.

**Como Diferenciar**

* CloudWatch observa.
* Auto Scaling ajusta capacidade.
* ELB distribui tráfego.
* Health checks removem destinos ruins.
* Multi-AZ reduz falha zonal.
* RTO e RPO guiam recuperação.

---

## Cuidados

NLB não fornece as mesmas regras de roteamento HTTP avançadas do ALB.

A escolha depende do protocolo e do tipo de aplicação.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

- [[Target Groups]]
- [[Health Checks]]
- [[Availability Zones (AZ)]]
- [[Application Load Balancer]]
- [[Amazon EC2 Auto Scaling]]
- [[Amazon CloudWatch]]
