Escalabilidade e Balanceamento de Carga é a combinação entre adicionar/remover capacidade e distribuir tráfego entre recursos saudáveis.

Na AWS, isso normalmente envolve [[Amazon EC2 Auto Scaling]] e [[Elastic Load Balancing]].

Escalabilidade e Balanceamento de Carga ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Escalabilidade e Balanceamento de Carga pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Escalabilidade e Balanceamento de Carga existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Como se Integram**

O fluxo típico é:

* Amazon CloudWatch observa métricas: ↓.
* Auto Scaling ajusta instâncias: ↓.
* novas instâncias entram no Target Group: ↓.
* Load Balancer distribui tráfego: ↓.
* Health Checks removem destinos ruins

**Por que Funciona**

Auto Scaling cuida da quantidade de capacidade.

Load Balancing cuida da distribuição de tráfego.

Health Checks cuidam de evitar destinos ruins.

CloudWatch cuida da observabilidade.

---

## Exemplo prático

Durante pico de tráfego, novas instâncias [[Amazon EC2|EC2]] são lançadas. Quando passam no health check, entram no target group. O ALB passa a distribuir requisições para elas.

Quando o pico termina, instâncias são removidas de forma controlada.

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

A aplicação precisa ser preparada para escala horizontal.

Sessões locais, arquivos locais e estado preso na instância dificultam balanceamento.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

- [[Amazon EC2 Auto Scaling]]
- [[Elastic Load Balancing]]
- [[Availability Zones (AZ)]]
- [[Application Load Balancer]]
- [[Amazon CloudWatch]]
