Rightsizing é o processo de ajustar recursos ao tamanho correto para a carga real.

Ele evita pagar por capacidade ociosa ou sofrer com recursos subdimensionados.

Rightsizing mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Rightsizing deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

A AWS cobra por consumo, e a equipe precisa estimar, acompanhar, controlar e otimizar gasto.

---

## Por que existe

Rightsizing existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

**Objetivo**

Rightsizing não significa sempre reduzir.

Significa alinhar recurso com necessidade real.

---

## Exemplo prático

* reduzir instância [[Amazon EC2|EC2]] com CPU baixa;
* aumentar banco com gargalo real;
* trocar tipo de volume EBS;
* reduzir retenção de logs;
* remover snapshots antigos;
* ajustar capacidade provisionada;
* escolher classe correta de [[Amazon S3|S3]].

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

Não reduza recursos olhando apenas custo.

É preciso considerar picos, sazonalidade, disponibilidade, SLA e performance.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Reduzir custo sem considerar disponibilidade e performance pode quebrar a aplicação.

---

## Relação com outras notas

**Relação com Observabilidade**

Rightsizing depende de métricas.

[[Amazon CloudWatch]], [[AWS Cost Explorer]] e [[AWS Trusted Advisor]] ajudam a identificar recursos subutilizados ou mal dimensionados.
