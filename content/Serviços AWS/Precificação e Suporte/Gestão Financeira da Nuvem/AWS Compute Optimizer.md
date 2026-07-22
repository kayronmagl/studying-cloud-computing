AWS Compute Optimizer é o serviço da AWS que analisa métricas de uso e recomenda ajustes de recursos computacionais.

Ele ajuda em [[Rightsizing]].


AWS Compute Optimizer mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## O que Recomenda

Pode recomendar ajustes para recursos como:

* instâncias EC2;
* Auto Scaling Groups;
* volumes EBS;
* funções Lambda;
* outros recursos compatíveis conforme suporte.

---

## Relação com Custo

Uma instância superdimensionada custa mais do que precisa.

Uma instância subdimensionada degrada performance.

Compute Optimizer ajuda a encontrar tamanho mais adequado com base em dados.

---

## Relação com CloudWatch

As recomendações dependem de métricas e histórico de uso.

Por isso, observabilidade é base para otimização.

---

## Cuidado

Recomendação não deve ser aplicada cegamente.

Considere picos, sazonalidade, requisitos de performance e janelas críticas.

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
