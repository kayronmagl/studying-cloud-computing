Governança de Custos na AWS é o conjunto de práticas usadas para manter custos visíveis, controlados e alinhados ao negócio.

Ela evita que a liberdade técnica da nuvem vire descontrole financeiro.

---

## Visão geral

Governança de Custos na AWS mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Componentes

Governança de custos envolve:

* contas bem organizadas;
* [[AWS Organizations]];
* [[AWS Control Tower]];
* [[Cost Allocation Tags]];
* [[AWS Cost Categories]];
* [[AWS Budgets]];
* políticas de acesso;
* revisão de recursos;
* processos de aprovação;
* [[AWS Service Catalog]];
* monitoramento de anomalias.

---

## Guardrails

Guardrails são proteções que orientam ou limitam ações.

Exemplo:


* somente regiões aprovadas
* tags obrigatórias
* orçamentos por projeto
* serviços permitidos
* limites de criação
* alertas de custo


---

## Relação com IAM

[[AWS Identity and Access Management (IAM)]] controla quem pode criar, alterar ou excluir recursos.

Sem controle de acesso, qualquer usuário pode gerar custo sem governança.

---

## Cuidado

Governança não deve bloquear aprendizado e inovação.

O objetivo é permitir uso seguro, rastreável e financeiramente responsável.

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
