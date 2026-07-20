AWS Savings Plans são modelos de desconto baseados em compromisso de uso por período.

Em troca de compromisso financeiro, a AWS oferece descontos em determinados tipos de uso elegíveis.

---

## Visão geral

AWS Savings Plans mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Ideia

Se uma empresa sabe que usará capacidade de computação de forma constante, pode assumir compromisso e pagar menos do que On-Demand.

---

## Quando Usar

Use quando há uso previsível e contínuo.

Exemplos:

* aplicações de produção sempre ligadas;
* workloads estáveis;
* serviços com base constante de computação.

---

## Diferença para Reserved Instances

[[Reserved Instances]] são mais ligadas a atributos de instância ou serviço.

Savings Plans são mais flexíveis dentro das regras do plano.

---

## Cuidado

Compromisso mal dimensionado pode gerar desperdício.

Antes de comprar, analise uso real no [[AWS Cost Explorer]].

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
