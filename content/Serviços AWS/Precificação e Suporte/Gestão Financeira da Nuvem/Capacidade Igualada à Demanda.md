Capacidade Igualada à Demanda é a prática de ajustar recursos ao volume real de uso.

Ela é uma ideia central da nuvem porque evita excesso de capacidade comprada antecipadamente.

Capacidade Igualada à Demanda mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Capacidade Igualada à Demanda deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

---

## Por que existe

Capacidade Igualada à Demanda existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

**Em Infraestrutura Tradicional**

Em data center tradicional, a empresa precisa comprar servidores antes da demanda.

Isso frequentemente gera dois problemas:

* capacidade demais: custo ocioso.
* capacidade de menos: indisponibilidade e lentidão.

**Em Nuvem**

Na AWS, serviços como [[Amazon EC2 Auto Scaling]], [[Application Auto Scaling]], [[AWS Lambda]], [[Amazon DynamoDB]] e [[Amazon S3]] permitem ajustar capacidade de forma mais próxima ao consumo.

---

## Exemplo prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

Capacidade igualada à demanda significa aproximar recursos do uso real.

Se a demanda cresce, a arquitetura aumenta capacidade. Se diminui, reduz. Isso evita tanto indisponibilidade por falta de recursos quanto desperdício por excesso permanente.

Na AWS, esse raciocínio aparece em Auto Scaling, serverless, serviços gerenciados e boas práticas de custo.

---

## Diferenças importantes

Não confunda reduzir custo com comprometer qualidade. Uma economia pode ser ruim se diminuir disponibilidade, segurança, recuperação ou desempenho além do aceitável.

---

## Cuidados

Igualar capacidade à demanda não significa escalar sem limites.

É preciso combinar elasticidade com [[AWS Budgets]], [[Amazon CloudWatch]], quotas, alarmes e governança.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

---

## Relação com outras notas

**Relação com Custo**

Ajustar capacidade reduz desperdício.

Mas exige métricas, limites, políticas de escala e revisão.

- [[Amazon EC2 Auto Scaling]]
- [[Application Auto Scaling]]
- [[AWS Lambda]]
- [[Amazon DynamoDB]]
- [[Amazon S3]]
- [[AWS Cost Explorer]]
- [[AWS Budgets]]
- [[AWS Billing and Cost Management]]
- [[AWS Trusted Advisor]]
- [[Amazon CloudWatch]]
