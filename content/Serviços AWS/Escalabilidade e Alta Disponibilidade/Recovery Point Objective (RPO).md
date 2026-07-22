Recovery Point Objective, ou RPO, é a quantidade máxima aceitável de perda de dados após uma falha.

Ele responde:


* até que ponto no passado posso perder dados?



Recovery Point Objective (RPO) ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Exemplo

Se o RPO é de 5 minutos, o sistema deve garantir que, em caso de desastre, no máximo 5 minutos de dados sejam perdidos.

---

## Relação com AWS

RPO influencia:

* frequência de backups;
* replicação;
* snapshots;
* [[Multi-AZ]];
* [[Arquitetura Multi-Region]];
* bancos gerenciados;
* streams;
* logs transacionais.

---

## RTO vs RPO

RTO fala de tempo para voltar.

RPO fala de perda de dados.


* RTO: quanto tempo para recuperar?
* RPO: quanto dado posso perder?


---

## Cuidado

RPO zero ou quase zero exige replicação forte e custo maior.

Nem todo workload justifica isso.

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
