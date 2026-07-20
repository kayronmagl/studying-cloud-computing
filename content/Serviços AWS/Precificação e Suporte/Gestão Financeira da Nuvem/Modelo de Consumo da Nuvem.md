Modelo de Consumo da Nuvem é o modelo em que recursos são usados sob demanda, medidos continuamente e cobrados conforme consumo.

Ele é a base econômica de serviços como [[Amazon EC2]], [[Amazon S3]], [[Amazon RDS]], [[Amazon CloudWatch]] e muitos outros.

---

## Visão geral

Modelo de Consumo da Nuvem mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Elementos

O modelo envolve:

* capacidade igualada à demanda;
* aquisição quase imediata;
* baixo custo de experimentação;
* equipes técnicas e financeiras colaborando;
* cobrança baseada em uso real;
* otimização contínua.

---

## Vantagem

A empresa não precisa comprar capacidade máxima antecipadamente.

Ela pode começar pequena, medir uso, escalar e otimizar.

---

## Risco

A mesma facilidade que permite criar recursos rapidamente também permite criar custo rapidamente.

Por isso, o modelo de consumo exige [[Governança de Custos na AWS]], [[AWS Budgets]], [[Cost Allocation Tags]] e revisão contínua.

---

## Exemplo

Uma aplicação pode usar [[Amazon EC2 Auto Scaling]] para aumentar instâncias em pico e reduzir depois.

Se bem configurado, isso aproxima custo da demanda.

Se mal configurado, pode escalar custo sem necessidade.

---

## Exemplo Prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Cuidados importantes

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

---

## Exemplo aplicado

O modelo de consumo da nuvem combina elasticidade, cobrança por uso e serviços sob demanda.

Uma aplicação pode usar pouca capacidade durante a madrugada e mais durante o horário comercial. O desenho correto aproveita essa variação em vez de pagar por capacidade parada o tempo todo.
