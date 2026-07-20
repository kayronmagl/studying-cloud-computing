Spot Instances permitem usar capacidade ociosa da AWS com desconto em relação a On-Demand.

O trade-off é que a AWS pode interromper a instância quando precisar recuperar a capacidade.

---

## Visão geral

Spot Instances mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Quando Usar

Use para workloads tolerantes a interrupção:

* processamento em lote;
* renderização;
* CI/CD;
* workers;
* análise;
* jobs paralelos;
* tarefas reprocessáveis.

---

## Quando Evitar

Evite para:

* banco primário;
* workloads stateful críticos;
* aplicações que não toleram interrupção;
* sistemas sem checkpoint.

---

## Relação com Arquitetura

Spot exige desenho resiliente:

* checkpoints;
* filas;
* retries;
* múltiplos tipos de instância;
* múltiplas AZs;
* Auto Scaling;
* interrupção tratada.

---

## Cuidado

Spot barato sem arquitetura tolerante a falha pode gerar indisponibilidade.

---

## Exemplo Prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Cuidados importantes

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

---

## Como entender isso

Este conceito pertence ao módulo de precificação, suporte e gestão financeira.

## Ponto central

A AWS cobra por consumo, e a equipe precisa estimar, acompanhar, controlar e otimizar gasto.

## Como Diferenciar

* Cost Explorer analisa custo.
* Budgets alerta.
* Tags organizam.
* CUR detalha.
* Savings Plans e Reserved Instances reduzem custo previsível.
* Spot reduz custo com risco de interrupção.

## Cuidado importante

Reduzir custo sem considerar disponibilidade e performance pode quebrar a aplicação.
