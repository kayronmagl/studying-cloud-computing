Compreender Custos da AWS é a capacidade de interpretar fatores de custo, tendências de uso e causas de variação.

Não basta ver que a fatura aumentou. É preciso entender o motivo.

Compreender Custos da AWS mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Compreender Custos da AWS deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

A AWS cobra por consumo, e a equipe precisa estimar, acompanhar, controlar e otimizar gasto.

---

## Por que existe

Compreender Custos da AWS existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

**Perguntas**

* qual serviço aumentou?
* o aumento veio de computação, armazenamento, tráfego ou logs?
* qual região mudou?
* qual conta ou projeto gerou custo?
* há tendência sazonal?
* há desperdício?

---

## Exemplo prático

Um aumento em [[Amazon EC2|EC2]] pode não ser apenas instância.

Pode envolver:

* volumes EBS;
* snapshots;
* transferência;
* Elastic IP;
* NAT Gateway;
* logs;
* load balancers.

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

Fatura agregada pode esconder causa real.

Compreender custos exige granularidade e contexto técnico.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Reduzir custo sem considerar disponibilidade e performance pode quebrar a aplicação.

---

## Relação com outras notas

**Ferramentas**

* [[AWS Cost Explorer]];
* [[Página de Faturas da AWS]];
* [[AWS Cost and Usage Report (CUR)]];
* relatórios de [[Reserved Instances]];
* gráficos por serviço, região, conta e tag.
