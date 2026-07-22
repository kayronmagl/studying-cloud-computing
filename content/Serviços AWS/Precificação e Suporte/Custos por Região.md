Custos por Região representam a variação de preços entre regiões AWS.

O mesmo serviço pode ter preço diferente dependendo da [[Regions (Regiões)|região]].


Custos por Região mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Por que Varia

Custos regionais refletem fatores como:

* infraestrutura local;
* energia;
* impostos;
* demanda;
* disponibilidade de serviço;
* custos operacionais;
* câmbio e mercado.

---

## Relação com Latência

Escolher região apenas por preço pode aumentar latência para usuários.

Escolher apenas por latência pode aumentar custo.

A decisão precisa equilibrar custo, performance, conformidade e disponibilidade.

---

## Exemplo

Hospedar no Brasil pode reduzir latência e atender requisitos locais, mas pode ter custo diferente de regiões dos EUA.

---

## Cuidado

Nem todo serviço está disponível em toda região.

Preço não é o único critério.

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

---

## Preço muda com arquitetura

[[Variabilidade de Custos]] fica clara quando você compara regiões, transferência de dados, modelos de compra e serviços.

---

## Custo de rede

[[Custo de Transferência de Dados]] aparece porque mover dados entre regiões, zonas ou para fora da AWS pode impactar a fatura.
