AWS Billing and Cost Management é o conjunto de ferramentas da AWS para gerenciar cobrança, custos, uso, orçamentos, relatórios e exportações.

Ele concentra a operação financeira da conta AWS.


AWS Billing and Cost Management mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Ferramentas

Inclui recursos como:

* [[AWS Cost Explorer]];
* [[AWS Budgets]];
* [[Data Exports da AWS]];
* [[AWS Cost and Usage Report (CUR)]];
* [[AWS Cost Anomaly Detection]];
* [[Cost Allocation Tags]].

---

## Perguntas que Responde

* quanto gastamos?
* com quais serviços?
* em quais regiões?
* em quais contas?
* qual projeto gerou custo?
* qual tendência?
* houve anomalia?


---

## Relação com FinOps

Billing and Cost Management é uma base técnica para [[FinOps]].

Ele fornece visibilidade para decisões de otimização.

---

## Cuidado

Sem tags e organização de contas, a análise financeira fica limitada.

Custo sem contexto vira apenas número.

---

## Relação com Gestão Financeira

* [[Gestão Financeira da Nuvem]];
* [[AWS Billing Dashboard]];
* [[Página de Faturas da AWS]];
* [[AWS Cost Categories]];
* [[Faturamento Consolidado da AWS]];

---

## Relação com Créditos

[[Créditos da AWS]] podem reduzir cobranças elegíveis, mas não substituem orçamento, alertas e acompanhamento de custos.

---

## Exemplo Prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Cuidados importantes

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

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
