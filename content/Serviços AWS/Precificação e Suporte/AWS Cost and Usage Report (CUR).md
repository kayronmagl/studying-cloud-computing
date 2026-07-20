AWS Cost and Usage Report, ou CUR, é um relatório detalhado de custo e uso da AWS.

Ele fornece dados granulares para análise financeira, auditoria e integração com ferramentas de BI ou FinOps.

---

## Visão geral

AWS Cost and Usage Report (CUR) mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Papel

CUR é usado quando o [[AWS Cost Explorer]] não é detalhado o suficiente.

Ele permite análises mais profundas por conta, serviço, recurso, tag, tipo de uso e período.

---

## Destino

Relatórios podem ser entregues em [[Amazon S3]] para análise posterior.

Podem ser consultados por ferramentas como Athena, Redshift ou sistemas externos.

---

## Uso

* chargeback;
* showback;
* análise por produto;
* auditoria;
* otimização;
* relatórios executivos;
* investigação de anomalias.

---

## Cuidado

CUR gera volume de dados.

É necessário governar retenção, particionamento, permissões e custo da própria análise.

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
