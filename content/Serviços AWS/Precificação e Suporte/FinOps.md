FinOps é a prática de governar custos de nuvem de forma colaborativa entre engenharia, operações, finanças e negócio.

O objetivo não é apenas reduzir custo. É maximizar valor do gasto em nuvem.

FinOps mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

FinOps deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

A AWS cobra por consumo, e a equipe precisa estimar, acompanhar, controlar e otimizar gasto.

---

## Por que existe

FinOps existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

**Princípios**

FinOps envolve:

* visibilidade;
* responsabilidade compartilhada;
* otimização contínua;
* decisões baseadas em dados;
* colaboração entre times;
* tags e alocação de custo;
* previsibilidade;
* automação.

**Ferramentas AWS**

* [[AWS Cost Explorer]];
* [[AWS Budgets]];
* [[Cost Allocation Tags]];
* [[AWS Cost Anomaly Detection]];
* [[AWS Trusted Advisor]];
* [[AWS Savings Plans]];
* [[Reserved Instances]].

**Showback e Chargeback**

Showback mostra custo por time ou projeto.

Chargeback repassa custo para áreas responsáveis.

---

## Exemplo prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Diferenças importantes

**Como Diferenciar**

* Cost Explorer analisa custo.
* Budgets alerta.
* Tags organizam.
* CUR detalha.
* Savings Plans e Reserved Instances reduzem custo previsível.
* Spot reduz custo com risco de interrupção.

---

## Cuidados

FinOps não deve virar apenas cobrança.

Se engenharia não entende os custos técnicos, a organização só descobre problemas na fatura.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Reduzir custo sem considerar disponibilidade e performance pode quebrar a aplicação.

---

## Relação com outras notas

- [[AWS Cost Explorer]]
- [[AWS Budgets]]
- [[Cost Allocation Tags]]
- [[AWS Cost Anomaly Detection]]
- [[AWS Trusted Advisor]]
- [[AWS Savings Plans]]
- [[Reserved Instances]]
- [[AWS Billing and Cost Management]]
