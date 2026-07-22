AWS Control Tower é um serviço da AWS para configurar e governar ambientes multi-conta.

Ele ajuda a criar uma landing zone com contas, guardrails e padrões iniciais de governança.


AWS Control Tower mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Relação com Custos

Control Tower não é apenas segurança ou organização.

Ele também ajuda na gestão financeira ao estruturar contas por ambiente, área ou workload.

Isso facilita:

* atribuição de custo;
* budgets por conta;
* faturamento consolidado;
* separação de responsabilidades;
* aplicação de guardrails.

---

## Relação com Organizations

[[AWS Control Tower]] usa [[AWS Organizations]] como base para organizar contas e unidades organizacionais.

---

## Cuidado

Control Tower estabelece estrutura.

A disciplina de tags, budgets, relatórios e otimização ainda precisa ser mantida pela organização.

---

## Exemplo Prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Cuidados importantes

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

---

## Relação com AWS CAF

Este conceito também aparece em discussões de adoção de nuvem dentro do [[AWS Cloud Adoption Framework (AWS CAF)]], especialmente quando a organização precisa criar governança, plataforma e operação consistentes para usar AWS em escala.
