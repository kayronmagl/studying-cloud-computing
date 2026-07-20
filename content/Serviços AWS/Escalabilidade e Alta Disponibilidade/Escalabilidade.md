Escalabilidade é a capacidade de um sistema ajustar sua capacidade conforme a demanda.

Um sistema escalável suporta aumento de tráfego, usuários, requisições, dados ou processamento sem degradar rapidamente.

---

## Visão geral

Escalabilidade ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Tipos

Existem dois tipos principais:

* [[Escalabilidade Vertical]];
* [[Escalabilidade Horizontal]].

Escala vertical aumenta a capacidade de um recurso existente. Escala horizontal adiciona mais recursos.

---

## Elasticidade

[[Elasticidade]] é a capacidade de escalar para cima e para baixo dinamicamente.

Na nuvem, elasticidade é importante porque evita pagar por capacidade ociosa durante períodos de baixa demanda.

---

## Relação com AWS

A AWS permite escalar usando:

* [[Amazon EC2 Auto Scaling]];
* [[Elastic Load Balancing]];
* [[AWS Lambda]];
* [[Amazon DynamoDB]];
* serviços gerenciados;
* filas como [[Amazon SQS]];
* métricas do [[Amazon CloudWatch]].

---

## Cuidado

Escalar não corrige arquitetura ruim.

Se o gargalo está no banco, aumentar instâncias web pode piorar o problema. Se o gargalo está em código ineficiente, escala pode apenas aumentar custo.

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
