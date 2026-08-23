Escalabilidade e Alta Disponibilidade na AWS é a área que explica como aplicações crescem, absorvem demanda, resistem a falhas e continuam disponíveis.

Ele vem depois de [[Redes na AWS]] e [[Segurança na AWS]] porque depende das duas camadas. Para escalar corretamente, os recursos precisam estar conectados por uma rede bem desenhada. Para operar com segurança, a escala precisa respeitar permissões, proteção de tráfego e auditoria.

Escalabilidade e Alta Disponibilidade na AWS ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Escalabilidade e Alta Disponibilidade na AWS pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Escalabilidade e Alta Disponibilidade na AWS existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Ordem Conceitual**

A sequência correta é:

* [[Redes na AWS]]: onde os recursos ficam e como se comunicam.
* [[Segurança na AWS]]: quem pode acessar e como proteger.
* Escalabilidade e Alta Disponibilidade na AWS: como crescer e continuar funcionando.

Escala sem rede adequada vira exposição ou gargalo.

Alta disponibilidade sem segurança pode manter um sistema vulnerável funcionando.

Segurança sem observabilidade não mostra quando a aplicação falha.

**Escalabilidade vs Alta Disponibilidade**

[[Escalabilidade]] é a capacidade de aumentar ou reduzir recursos conforme demanda.

[[Alta Disponibilidade]] é a capacidade de permanecer operacional mesmo quando componentes falham.

Esses conceitos se conectam, mas não são iguais.

Exemplo: uma aplicação pode escalar para cem instâncias em uma única zona. Ela escala, mas ainda pode cair se a zona falhar.

**Serviços Principais**

Esta área conecta:

* [[Amazon CloudWatch]];
* [[Amazon EC2 Auto Scaling]];
* [[Elastic Load Balancing]];
* [[Auto Scaling Groups]];
* [[Application Load Balancer]];
* [[Network Load Balancer]];
* [[Gateway Load Balancer]];
* [[Health Checks]];
* [[Target Groups]];
* [[Availability Zones (AZ)]];
* [[Amazon Route 53]];
* [[Multi-AZ]].

A arquitetura madura nasce da integração entre esses componentes.

**Além de [[Amazon EC2|EC2]]**

Escalabilidade na AWS não se limita a [[Amazon EC2|EC2]].

Serviços como [[Application Auto Scaling]], [[AWS Auto Scaling]] e [[Predictive Scaling]] ajudam a pensar escala em múltiplas camadas da aplicação.

Alta disponibilidade também precisa considerar [[Recovery Time Objective (RTO)]], [[Recovery Point Objective (RPO)]], [[Arquitetura Multi-AZ]], [[Arquitetura Multi-Region]], [[Route 53 Health Checks]] e [[Failover Routing]].

A resiliência de aplicação depende ainda de padrões como [[Timeouts]], [[Retries com Backoff Exponencial]], [[Circuit Breaker]], [[Bulkhead Pattern]] e [[Graceful Degradation]].

---

## Exemplo prático

Uma aplicação pode aumentar capacidade quando CPU, fila ou requisições crescem, distribuir tráfego entre instâncias e remover destinos não saudáveis. Nesse cenário, Escalabilidade e Alta Disponibilidade na AWS ajuda a manter resposta e disponibilidade.

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

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Conceitos que completam o assunto**

O [[AWS Fault Injection Service (FIS)]] ajuda a testar o comportamento da arquitetura diante de falhas. Já [[Escalabilidade e Balanceamento de Carga]] e [[Integração CloudWatch Auto Scaling e ELB]] mostram como observabilidade, distribuição de tráfego e ajuste de capacidade trabalham juntos.
