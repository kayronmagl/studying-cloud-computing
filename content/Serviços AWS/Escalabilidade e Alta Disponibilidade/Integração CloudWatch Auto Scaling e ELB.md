Integração CloudWatch Auto Scaling e ELB é o padrão em que observabilidade, escala automática e balanceamento trabalham juntos.

É uma das composições mais importantes para aplicações web na AWS.

Integração CloudWatch Auto Scaling e ELB ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Integração CloudWatch Auto Scaling e ELB pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Integração CloudWatch Auto Scaling e ELB existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Componentes**

* [[Amazon CloudWatch]] observa métricas.
* [[Alarmes do Amazon CloudWatch]] detectam condições.
* [[Amazon EC2 Auto Scaling]] ajusta capacidade.
* [[Auto Scaling Groups]] lançam ou removem instâncias.
* [[Elastic Load Balancing]] distribui tráfego.
* [[Health Checks]] validam destinos.
* [[Target Groups]] organizam instâncias.

**Fluxo**

* tráfego aumenta: ↓.
* métrica sobe: ↓.
* alarme muda de estado: ↓.
* Auto Scaling lança instância: ↓.
* instância inicializa: ↓.
* health check aprova: ↓.
* load balancer envia tráfego

**Por que é Importante**

Esse padrão transforma infraestrutura em sistema adaptativo.

A arquitetura deixa de depender apenas de intervenção manual.

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

A integração depende de boas métricas, health checks corretos e limites de escala bem definidos.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

- [[Amazon CloudWatch]]
- [[Alarmes do Amazon CloudWatch]]
- [[Amazon EC2 Auto Scaling]]
- [[Auto Scaling Groups]]
- [[Elastic Load Balancing]]
- [[Health Checks]]
- [[Target Groups]]
- [[Availability Zones (AZ)]]
- [[Application Load Balancer]]
