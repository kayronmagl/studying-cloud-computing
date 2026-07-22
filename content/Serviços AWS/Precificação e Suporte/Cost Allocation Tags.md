Cost Allocation Tags são tags usadas para organizar custos na AWS.

A documentação da AWS explica que relatórios de alocação de custos incluem custos com tags e sem tags, permitindo organizar cobranças por atributos como aplicação.


Cost Allocation Tags mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Por que Importam

Sem tags, custos aparecem por serviço ou conta, mas não necessariamente por projeto, time ou ambiente.

Com tags, é possível responder:


* quanto custa o projeto X?
* quanto custa produção?
* quanto custa desenvolvimento?
* qual time gerou esse gasto?


---

## Exemplos de Tags

* `Project`;
* `Environment`;
* `Owner`;
* `CostCenter`;
* `Application`;
* `Team`.

---

## Relação com FinOps

Tags são base para [[FinOps]], showback e chargeback.

---

## Cuidado

Tags precisam de padrão.

Se um time usa `prod`, outro usa `production` e outro não usa tag, a análise fica inconsistente.

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

Este conceito pertence à camada de precificação, suporte e gestão financeira.

## Ponto central

Na AWS, custo depende de uso, região, serviço, armazenamento, requisições, tráfego, logs, suporte e compromissos de uso.

## Como Diferenciar

* Pricing Calculator estima custo antes.
* Cost Explorer analisa custo real.
* Budgets alerta sobre limites.
* Tags ajudam alocação de custo.
* Trusted Advisor recomenda melhorias.
* Support Plans mudam nível de suporte.

## Cuidado importante

Pay-as-you-go não significa barato. Significa pagar conforme uso. Uso sem controle pode ficar caro.
