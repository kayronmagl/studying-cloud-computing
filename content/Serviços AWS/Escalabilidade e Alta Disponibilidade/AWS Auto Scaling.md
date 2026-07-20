AWS Auto Scaling é uma abordagem e serviço de coordenação para configurar políticas de escala em múltiplos recursos AWS.

Ele ajuda a enxergar escala como uma propriedade da aplicação, não apenas de instâncias.

---

## Visão geral

AWS Auto Scaling ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Diferença para EC2 Auto Scaling

[[Amazon EC2 Auto Scaling]] é específico para instâncias EC2.

[[Application Auto Scaling]] cobre outros recursos escaláveis.

AWS Auto Scaling pode ajudar a organizar planos de escala para múltiplos recursos.

---

## Ideia Principal

Uma aplicação completa pode precisar escalar:

* instâncias web;
* containers;
* tabelas DynamoDB;
* réplicas;
* workers;
* filas;
* serviços de backend.

O objetivo é alinhar capacidade entre camadas.

---

## Relação com Observabilidade

Sem [[Amazon CloudWatch]], escalabilidade automática fica cega.

Métricas são usadas para decidir quando crescer ou reduzir.

---

## Cuidado

Automatizar escala sem limites pode aumentar custo rapidamente.

Toda política precisa de mínimo, máximo, métrica, objetivo e observação.

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
