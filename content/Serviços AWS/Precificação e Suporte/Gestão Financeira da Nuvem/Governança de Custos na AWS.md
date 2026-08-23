Governança de Custos na AWS é o conjunto de práticas usadas para manter custos visíveis, controlados e alinhados ao negócio.

Ela evita que a liberdade técnica da nuvem vire descontrole financeiro.

Governança de Custos na AWS mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Governança de Custos na AWS deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

---

## Por que existe

Governança de Custos na AWS existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

**Componentes**

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

**Guardrails**

Guardrails são proteções que orientam ou limitam ações.

Exemplo:

* somente regiões aprovadas
* tags obrigatórias
* orçamentos por projeto
* serviços permitidos
* limites de criação
* alertas de custo

---

## Exemplo prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Diferenças importantes

Não confunda reduzir custo com comprometer qualidade. Uma economia pode ser ruim se diminuir disponibilidade, segurança, recuperação ou desempenho além do aceitável.

---

## Cuidados

Governança não deve bloquear aprendizado e inovação.

O objetivo é permitir uso seguro, rastreável e financeiramente responsável.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

---

## Relação com outras notas

**Relação com [[AWS Identity and Access Management (IAM)|IAM]]**

[[AWS Identity and Access Management (IAM)]] controla quem pode criar, alterar ou excluir recursos.

Sem controle de acesso, qualquer usuário pode gerar custo sem governança.

**Relação com AWS CAF**

Este conceito também aparece em discussões de adoção de nuvem dentro do [[AWS Cloud Adoption Framework (AWS CAF)]], especialmente quando a organização precisa criar governança, plataforma e operação consistentes para usar AWS em escala.
