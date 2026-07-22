AWS Basic Support é o suporte incluído para todos os clientes AWS.

Ele é adequado para início, aprendizado e acesso básico a recursos de conta e cobrança.


AWS Basic Support mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## O que Representa

Basic Support não é um plano operacional completo para produção crítica.

Ele oferece acesso a documentação, fóruns/comunidade, suporte de conta e cobrança e recursos básicos disponíveis a todos.

---

## Quando Basta

Pode bastar para:

* estudos;
* laboratórios;
* contas pessoais;
* experimentação;
* ambientes sem criticidade.

---

## Quando não Basta

Para workloads de produção, incidentes críticos e necessidade de tempo de resposta técnico, planos pagos como [[AWS Business Support+]] ou superiores devem ser avaliados.

---

## Boa Prática

Mesmo em Basic Support, configure [[AWS Budgets]], [[AWS Health Dashboard]], [[Service Quotas]] e observabilidade.

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
