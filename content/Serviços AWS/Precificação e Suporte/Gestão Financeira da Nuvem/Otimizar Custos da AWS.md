Otimizar Custos da AWS é a capacidade de reduzir desperdício e melhorar relação entre gasto e valor entregue.

Otimização não significa cortar recursos sem critério.

Significa ajustar arquitetura, modelos de compra, tamanhos, retenção, armazenamento e padrões de uso.

---

## Visão geral

Otimizar Custos da AWS mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Ferramentas

* [[AWS Cost Explorer]];
* [[AWS Compute Optimizer]];
* [[AWS Trusted Advisor]];
* [[Rightsizing]];
* [[AWS Savings Plans]];
* [[Reserved Instances]];
* [[Spot Instances]];
* [[S3 Intelligent-Tiering]];
* [[AWS Instance Scheduler]].

---

## Exemplos de Otimização

* reduzir instâncias subutilizadas;
* trocar tipo de instância;
* remover volumes órfãos;
* encerrar ambientes fora de horário;
* ajustar retenção de logs;
* mover objetos S3 para classes adequadas;
* comprar Savings Plans para uso constante;
* usar Spot para workloads tolerantes a interrupção.

---

## Cuidado

Otimização sem métrica pode causar indisponibilidade.

Toda redução precisa considerar performance, disponibilidade, segurança e experiência do usuário.

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
