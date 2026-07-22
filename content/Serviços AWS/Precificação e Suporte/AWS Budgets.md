AWS Budgets permite criar orçamentos e alertas para custo, uso, cobertura e utilização.

A documentação da AWS indica que Budgets pode rastrear custos e uso e também monitorar utilização e cobertura de Reserved Instances e Savings Plans.


AWS Budgets mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Uso

Budgets pode alertar quando:

* custo real ultrapassa limite;
* custo previsto ultrapassa limite;
* uso de serviço passa de um valor;
* cobertura de Savings Plans cai;
* utilização de compromisso fica baixa.

---

## Exemplo

* budget mensal: R$ 100
* alerta em 50%
* alerta em 80%
* alerta em 100%


---

## Por que é Essencial

Budgets é uma das primeiras proteções em contas de estudo e produção.

Ele não impede todo gasto, mas alerta cedo.

---

## Cuidado

Alertas precisam de destinatários corretos.

Um alerta ignorado não protege orçamento.

---

## Relação com Gestão Financeira

* [[Controlar Custos da AWS]];
* [[Alertas de Orçamentos da AWS]];

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

---

## Relação com alarmes de faturamento

AWS Budgets é usado para criar orçamentos e alertas de custo, uso ou previsão.

Mas quando a pergunta que fala especificamente em produto que cria um alarme que envia notificação quando limite de faturamento é excedido, a alternativa esperada pode ser [[Amazon CloudWatch]], por causa dos billing alarms.

---

## Como diferenciar

* quer orçamento, previsão e acompanhamento financeiro: AWS Budgets.
* quer alarme baseado em métrica de billing: Amazon CloudWatch.
