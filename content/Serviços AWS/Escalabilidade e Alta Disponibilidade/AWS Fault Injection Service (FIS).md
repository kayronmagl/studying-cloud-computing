AWS Fault Injection Service, ou AWS FIS, é o serviço da AWS para executar experimentos controlados de falha.

Ele é usado para testar resiliência de workloads.

AWS Fault Injection Service (FIS) ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

AWS Fault Injection Service (FIS) pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

AWS Fault Injection Service (FIS) existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Objetivo**

FIS ajuda a validar se a arquitetura realmente suporta falhas.

Em vez de assumir que Auto Scaling, health checks e failover funcionam, a equipe testa.

**Exemplos de Experimento**

* interromper instâncias;
* aumentar latência;
* simular indisponibilidade;
* limitar recursos;
* validar alarmes;
* observar recuperação.

---

## Exemplo prático

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

Experimentos precisam de limites, ambiente adequado, plano de parada e autorização.

Testar falha sem controle pode causar incidente real.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com Chaos Engineering**

FIS se relaciona com práticas de engenharia do caos, nas quais falhas controladas são usadas para revelar fragilidades antes que incidentes reais aconteçam.

**Relação com AWS**

Testes podem validar integração entre:

* [[Amazon CloudWatch]];
* [[Elastic Load Balancing]];
* [[Amazon EC2 Auto Scaling]];
* [[Health Checks]];
* [[Auto Scaling Groups]];
* [[Availability Zones (AZ)]].
