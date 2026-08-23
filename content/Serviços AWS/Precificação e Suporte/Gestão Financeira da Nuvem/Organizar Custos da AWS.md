Organizar Custos da AWS é a capacidade de estruturar dados financeiros para entender quem gerou gasto e por quê.

A organização de custos depende de contas, tags, categorias e padrões de governança.

Organizar Custos da AWS mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Organizar Custos da AWS deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

A AWS cobra por consumo, e a equipe precisa estimar, acompanhar, controlar e otimizar gasto.

---

## Por que existe

Organizar Custos da AWS existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

**Tags**

Tags permitem atribuir custo a dimensões como:

* Project
* Environment
* Owner
* Team
* CostCenter
* Application

Quando ativadas para alocação de custos, aparecem em ferramentas como [[AWS Cost Explorer]] e [[AWS Cost and Usage Report (CUR)]].

**Categorias de Custo**

[[AWS Cost Categories]] permite criar agrupamentos financeiros acima das tags e contas.

Isso ajuda a mapear custos para linhas de negócio, produtos ou centros financeiros.

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

Organização precisa começar cedo.

Corrigir tags retroativamente é difícil e geralmente incompleto.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Reduzir custo sem considerar disponibilidade e performance pode quebrar a aplicação.

---

## Relação com outras notas

**Ferramentas**

* [[Cost Allocation Tags]];
* [[AWS Cost Categories]];
* [[AWS Organizations]];
* [[Faturamento Consolidado da AWS]];
* contas por ambiente;
* contas por projeto;
* tags padronizadas.
