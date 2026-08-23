Spot Instances permitem usar capacidade ociosa da AWS com desconto em relação a On-Demand.

O trade-off é que a AWS pode interromper a instância quando precisar recuperar a capacidade.

Spot Instances mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Spot Instances deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

A AWS cobra por consumo, e a equipe precisa estimar, acompanhar, controlar e otimizar gasto.

---

## Por que existe

Spot Instances existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

O funcionamento depende de medição de uso, cobrança, categorização, alertas, relatórios, planos e decisões de operação. Ao estudar Spot Instances, relacione sempre consumo técnico com impacto financeiro.

---

## Exemplo prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Diferenças importantes

**Quando Usar**

Use para workloads tolerantes a interrupção:

* processamento em lote;
* renderização;
* CI/CD;
* workers;
* análise;
* jobs paralelos;
* tarefas reprocessáveis.

**Quando Evitar**

Evite para:

* banco primário;
* workloads stateful críticos;
* aplicações que não toleram interrupção;
* sistemas sem checkpoint.

**Como Diferenciar**

* Cost Explorer analisa custo.
* Budgets alerta.
* Tags organizam.
* CUR detalha.
* Savings Plans e Reserved Instances reduzem custo previsível.
* Spot reduz custo com risco de interrupção.

---

## Cuidados

Spot barato sem arquitetura tolerante a falha pode gerar indisponibilidade.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Reduzir custo sem considerar disponibilidade e performance pode quebrar a aplicação.

---

## Relação com outras notas

**Relação com Arquitetura**

Spot exige desenho resiliente:

* checkpoints;
* filas;
* retries;
* múltiplos tipos de instância;
* múltiplas AZs;
* Auto Scaling;
* interrupção tratada.

- [[AWS Cost Explorer]]
- [[AWS Budgets]]
- [[AWS Billing and Cost Management]]
- [[AWS Trusted Advisor]]
