AWS Pricing Calculator é a ferramenta da AWS para estimar custos de workloads.

Ela permite montar cenários, escolher serviços, definir parâmetros de uso e gerar estimativas.

A AWS descreve a ferramenta como uma forma de explorar serviços AWS e criar estimativas de custo para casos de uso.

---

## Visão geral

AWS Pricing Calculator mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Quando Usar

Use antes de:

* criar arquitetura;
* comparar alternativas;
* propor projeto;
* migrar ambiente;
* aumentar capacidade;
* escolher região;
* discutir orçamento.

---

## Exemplo

Uma estimativa pode incluir:

* instâncias [[Amazon EC2]];
* volumes [[Amazon EBS]];
* banco [[Amazon RDS]];
* tráfego de rede;
* armazenamento [[Amazon S3]];
* suporte;
* data transfer.

---

## Limite

A calculadora estima.

A fatura real depende de uso real, tráfego, variação de arquitetura, logs, requisições, mudanças e comportamento da aplicação.

---

## Boa Prática

Use a calculadora como hipótese inicial e depois compare com dados reais no [[AWS Cost Explorer]].

---

## Exemplo Prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Cuidados importantes

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

---

## Explicação principal

AWS Pricing Calculator serve para estimar custo antes de criar a arquitetura.

Ela não mostra cobrança real; ela simulo cenários.

## Quando Usar na prática

* antes de migrar workload;
* antes de propor arquitetura;
* para comparar serviços;
* para estimar custo mensal;
* para justificar decisões.

## Limite na prática

A estimativa depende das informações fornecidas. Se tráfego, logs, armazenamento ou uso real forem diferentes, a fatura também será.

## Cuidado importante

A calculadora não substitui Cost Explorer. Calculator estima antes; Cost Explorer analisa depois do uso real.
