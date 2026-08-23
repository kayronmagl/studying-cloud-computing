Recovery Point Objective, ou RPO, é a quantidade máxima aceitável de perda de dados após uma falha.

Ele responde:

* até que ponto no passado posso perder dados?

Recovery Point Objective (RPO) ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Recovery Point Objective (RPO) pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Recovery Point Objective (RPO) existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**RTO vs RPO**

RTO fala de tempo para voltar.

RPO fala de perda de dados.

* RTO: quanto tempo para recuperar?
* RPO: quanto dado posso perder?

---

## Exemplo prático

Se o RPO é de 5 minutos, o sistema deve garantir que, em caso de desastre, no máximo 5 minutos de dados sejam perdidos.

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

RPO zero ou quase zero exige replicação forte e custo maior.

Nem todo workload justifica isso.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com AWS**

RPO influencia:

* frequência de backups;
* replicação;
* snapshots;
* [[Multi-AZ]];
* [[Arquitetura Multi-Region]];
* bancos gerenciados;
* streams;
* logs transacionais.
