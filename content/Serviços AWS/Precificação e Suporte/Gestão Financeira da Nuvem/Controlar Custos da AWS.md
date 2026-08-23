Controlar Custos da AWS é a capacidade de estabelecer limites, alertas, permissões e mecanismos de governança.

Controle não significa impedir todo gasto. Significa evitar surpresa e manter uso dentro de limites aceitáveis.

Controlar Custos da AWS mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Controlar Custos da AWS deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

A AWS cobra por consumo, e a equipe precisa estimar, acompanhar, controlar e otimizar gasto.

---

## Por que existe

Controlar Custos da AWS existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

**Orçamentos**

[[AWS Budgets]] permite criar limites de custo ou uso e receber alertas quando o gasto real ou previsto se aproxima do limite.

**Controle de Acesso**

[[AWS Identity and Access Management (IAM)|IAM]] controla quem pode criar recursos caros ou alterar configurações de billing.

Isso é parte da governança financeira.

---

## Exemplo prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Diferenças importantes

**Como Diferenciar**

* Cost Explorer analisa custo.
* Budgets alerta.
* Tags organizam.
* CUR detalha.
* Savings Plans e Reserved Instances reduzem custo previsível.
* Spot reduz custo com risco de interrupção.

---

## Cuidados

Controle tardio é menos eficaz.

O ideal é aplicar guardrails antes que times criem recursos em produção.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Reduzir custo sem considerar disponibilidade e performance pode quebrar a aplicação.

---

## Relação com outras notas

**Ferramentas**

* [[AWS Budgets]];
* [[Alertas de Orçamentos da AWS]];
* [[AWS Organizations]];
* [[AWS Identity and Access Management (IAM)]];
* [[AWS Control Tower]];
* [[AWS Service Catalog]];
* [[Service Quotas]];
* políticas internas.
