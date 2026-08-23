AWS Health Dashboard mostra eventos de saúde relacionados à AWS e à conta.

Ele ajuda a entender se há eventos operacionais afetando serviços, regiões ou recursos.

AWS Health Dashboard mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

AWS Health Dashboard deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

A AWS cobra por consumo, e a equipe precisa estimar, acompanhar, controlar e otimizar gasto.

---

## Por que existe

AWS Health Dashboard existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

**Função**

O dashboard pode informar:

* eventos de serviço;
* manutenção;
* degradações;
* problemas regionais;
* impactos específicos da conta;
* notificações operacionais.

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

Nem todo problema da aplicação aparece no Health Dashboard.

Se a aplicação está mal configurada, o evento pode ser local ao workload.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Reduzir custo sem considerar disponibilidade e performance pode quebrar a aplicação.

---

## Relação com outras notas

**Relação com Incidentes**

Durante uma falha, a equipe precisa saber se o problema está na aplicação ou em um serviço AWS.

AWS Health ajuda nessa investigação.

**Relação com Suporte**

Em eventos relevantes, suporte e saúde operacional se complementam.

A equipe pode abrir [[Support Case]] se precisar de orientação adicional.
