Reserved Instances, ou RIs, são compromissos de uso que oferecem desconto em troca de reserva por período.

Elas são comuns em serviços como [[Amazon EC2]] e bancos, dependendo do serviço.

Reserved Instances mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Reserved Instances deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

A AWS cobra por consumo, e a equipe precisa estimar, acompanhar, controlar e otimizar gasto.

---

## Por que existe

RIs podem reduzir custo em comparação com On-Demand.

---

## Como funciona

O funcionamento depende de medição de uso, cobrança, categorização, alertas, relatórios, planos e decisões de operação. Ao estudar Reserved Instances, relacione sempre consumo técnico com impacto financeiro.

---

## Exemplo prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Diferenças importantes

**Quando Usar**

Use quando o workload é previsível e constante.

Exemplo: servidores de produção que ficam ligados o tempo todo.

**Diferença para Savings Plans**

[[AWS Savings Plans]] tendem a oferecer mais flexibilidade em certos cenários de computação.

RIs podem ser específicas conforme serviço, instância, região e atributos.

**Como Diferenciar**

* Cost Explorer analisa custo.
* Budgets alerta.
* Tags organizam.
* CUR detalha.
* Savings Plans e Reserved Instances reduzem custo previsível.
* Spot reduz custo com risco de interrupção.

---

## Cuidados

Comprar RIs sem analisar uso pode prender a organização em compromisso ruim.

Sempre avalie cobertura e utilização.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Reduzir custo sem considerar disponibilidade e performance pode quebrar a aplicação.

---

## Relação com outras notas

**Relação com Gestão Financeira**

* [[Relatórios de Instâncias Reservadas]];
