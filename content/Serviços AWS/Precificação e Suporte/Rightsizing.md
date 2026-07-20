Rightsizing é o processo de ajustar recursos ao tamanho correto para a carga real.

Ele evita pagar por capacidade ociosa ou sofrer com recursos subdimensionados.

---

## Visão geral

Rightsizing mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Exemplos

* reduzir instância EC2 com CPU baixa;
* aumentar banco com gargalo real;
* trocar tipo de volume EBS;
* reduzir retenção de logs;
* remover snapshots antigos;
* ajustar capacidade provisionada;
* escolher classe correta de S3.

---

## Relação com Observabilidade

Rightsizing depende de métricas.

[[Amazon CloudWatch]], [[AWS Cost Explorer]] e [[AWS Trusted Advisor]] ajudam a identificar recursos subutilizados ou mal dimensionados.

---

## Cuidado

Não reduza recursos olhando apenas custo.

É preciso considerar picos, sazonalidade, disponibilidade, SLA e performance.

---

## Objetivo

Rightsizing não significa sempre reduzir.

Significa alinhar recurso com necessidade real.

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
