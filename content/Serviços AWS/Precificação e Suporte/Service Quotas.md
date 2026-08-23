Service Quotas é o serviço da AWS para visualizar e gerenciar quotas de serviços.

A documentação da AWS explica que contas possuem quotas padrão, antes chamadas de limites, e que muitas quotas são específicas por região; algumas podem ser aumentadas e outras não.

Service Quotas mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Service Quotas deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

A AWS cobra por consumo, e a equipe precisa estimar, acompanhar, controlar e otimizar gasto.

---

## Por que existe

Quotas afetam escala.

Exemplos:

* número de instâncias;
* quantidade de VPCs;
* limites de load balancers;
* limites de funções;
* limites de filas;
* limites de IPs;
* capacidade regional.

---

## Como funciona

**Solicitação de Aumento**

Muitas quotas permitem solicitar aumento pelo console.

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

Nem toda quota pode ser aumentada.

Algumas exigem arquitetura alternativa.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Reduzir custo sem considerar disponibilidade e performance pode quebrar a aplicação.

---

## Relação com outras notas

**Relação com Alta Disponibilidade**

Uma arquitetura pode falhar ao escalar se atingir quotas.

Por isso, quotas precisam ser avaliadas antes de picos, campanhas e migrações.

- [[AWS Cost Explorer]]
- [[AWS Budgets]]
- [[AWS Billing and Cost Management]]
- [[AWS Trusted Advisor]]
