AWS Cost Explorer é a ferramenta da AWS para visualizar e analisar custos e uso ao longo do tempo.

Ele ajuda a entender de onde vem a fatura, quais serviços estão consumindo mais, como os custos mudam com o tempo e quais tendências precisam de atenção.


Cost Explorer é análise de custo.

Ele não serve principalmente para estimar um projeto antes de criar recursos. Para estimativa antes do uso, o serviço mais associado é [[AWS Pricing Calculator]].

No Cost Explorer, você analisa custos por serviço, conta, região, tag, tipo de uso, opção de compra e período. Ele também pode mostrar dados recentes e previsões, dependendo da configuração da conta.

---

## Diferença para ferramentas parecidas

| Ferramenta | Função principal |
|---|---|
| AWS Pricing Calculator | Estimar custos antes do uso |
| AWS Cost Explorer | Visualizar e analisar custos e uso ao longo do tempo |
| AWS Budgets | Criar orçamentos e alertas |
| AWS Cost and Usage Report | Relatório detalhado de custos e uso |

---

## Como Diferenciar


---

## Exemplo aplicado

Imagine que a fatura aumentou este mês.

No Cost Explorer, você pode investigar se o aumento veio de EC2, S3, transferência de dados, NAT Gateway, uma região específica ou uma conta da organização.

Essa visão ajuda a sair do “a conta ficou cara” para uma investigação concreta do que mudou.

---

## Diferença para orçamento

Cost Explorer responde melhor à pergunta “onde meu custo está acontecendo?”.

AWS Budgets responde melhor à pergunta “quando devo ser avisado se o custo passar de um limite?”.

Os dois se complementam. Você pode usar Budgets para receber alerta e depois abrir Cost Explorer para investigar qual serviço, conta, região ou tag causou o aumento.

---

## Exemplo de investigação

Um uso comum é abrir o Cost Explorer depois de receber um alerta de orçamento.

A equipe pode filtrar por serviço, região, conta, tag ou tipo de uso. Assim, ela descobre se o aumento veio de EC2, S3, transferência de dados, NAT Gateway, banco de dados ou outro componente.

Essa análise transforma a fatura em informação útil para decisão.

---

## Cuidado importante

Cost Explorer mostra o que aconteceu com os custos e ajuda a investigar tendências.

Ele não substitui um orçamento bem definido. Para receber alertas quando o custo passa de um limite, AWS Budgets costuma ser mais adequado.

Na prática, Budgets avisa e Cost Explorer ajuda a entender o motivo.
