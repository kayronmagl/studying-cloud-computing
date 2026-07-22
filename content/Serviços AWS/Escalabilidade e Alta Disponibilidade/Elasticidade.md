Elasticidade é a capacidade de aumentar ou reduzir recursos automaticamente conforme a demanda.

Ela é uma característica central da computação em nuvem.


Elasticidade ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Diferença para Escalabilidade

[[Escalabilidade]] é a capacidade de crescer.

Elasticidade é crescer e reduzir dinamicamente.

Um sistema pode ser escalável manualmente, mas não elástico.

---

## Exemplo

Uma loja virtual aumenta instâncias durante a Black Friday e reduz depois.

Se isso acontece automaticamente com [[Amazon EC2 Auto Scaling]], a arquitetura está usando elasticidade.

---

## Benefício

Elasticidade reduz custo de ociosidade e melhora resposta a picos.

Ela combina com [[Pay-as-you-go]], porque recursos podem ser ajustados conforme uso.

---

## Cuidado

Elasticidade precisa de limites.

Sem máximo configurado, uma falha ou ataque pode escalar custo rapidamente.

---

## Relação com Gestão Financeira

* [[AWS Instance Scheduler]];

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
