Custo de Transferência de Dados é um dos fatores mais importantes e mais esquecidos na precificação de nuvem.

Na AWS, transferência pode ter custo dependendo da direção, origem, destino, região, zona, serviço e volume.

Custo de Transferência de Dados mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Custo de Transferência de Dados deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

A AWS cobra por consumo, e a equipe precisa estimar, acompanhar, controlar e otimizar gasto.

---

## Por que existe

Custo de Transferência de Dados existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

**Tipos**

Podem existir custos em:

* saída para internet;
* transferência entre regiões;
* transferência entre AZs;
* tráfego via NAT Gateway;
* entrega por CDN;
* replicação;
* movimentação entre serviços.

---

## Exemplo prático

Uma aplicação pode ter instâncias baratas, mas alto custo de tráfego se envia muitos dados para a internet ou cruza regiões desnecessariamente.

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

Nunca estime custo olhando apenas computação e armazenamento.

Transferência de dados pode ser relevante em aplicações web, streaming, backups e analytics.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Reduzir custo sem considerar disponibilidade e performance pode quebrar a aplicação.

---

## Relação com outras notas

**Relação com Arquitetura**

[[Redes na AWS]] afeta custo.

Arquiteturas com NAT Gateway, multi-AZ, multi-region e tráfego intenso precisam considerar data transfer.
