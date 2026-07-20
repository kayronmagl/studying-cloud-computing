Capacidade Igualada à Demanda é a prática de ajustar recursos ao volume real de uso.

Ela é uma ideia central da nuvem porque evita excesso de capacidade comprada antecipadamente.

---

## Visão geral

Capacidade Igualada à Demanda mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Em Infraestrutura Tradicional

Em data center tradicional, a empresa precisa comprar servidores antes da demanda.

Isso frequentemente gera dois problemas:


* capacidade demais: custo ocioso.
* capacidade de menos: indisponibilidade e lentidão.


---

## Em Nuvem

Na AWS, serviços como [[Amazon EC2 Auto Scaling]], [[Application Auto Scaling]], [[AWS Lambda]], [[Amazon DynamoDB]] e [[Amazon S3]] permitem ajustar capacidade de forma mais próxima ao consumo.

---

## Relação com Custo

Ajustar capacidade reduz desperdício.

Mas exige métricas, limites, políticas de escala e revisão.

---

## Cuidado

Igualar capacidade à demanda não significa escalar sem limites.

É preciso combinar elasticidade com [[AWS Budgets]], [[Amazon CloudWatch]], quotas, alarmes e governança.

---

## Exemplo Prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Cuidados importantes

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

---

## Exemplo aplicado

Capacidade igualada à demanda significa aproximar recursos do uso real.

Se a demanda cresce, a arquitetura aumenta capacidade. Se diminui, reduz. Isso evita tanto indisponibilidade por falta de recursos quanto desperdício por excesso permanente.

Na AWS, esse raciocínio aparece em Auto Scaling, serverless, serviços gerenciados e boas práticas de custo.
