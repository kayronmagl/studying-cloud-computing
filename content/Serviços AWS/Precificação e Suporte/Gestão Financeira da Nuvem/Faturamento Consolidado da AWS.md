Faturamento Consolidado da AWS permite reunir cobranças de múltiplas contas em uma organização.

Ele é usado com [[AWS Organizations]] para centralizar billing e facilitar gestão financeira.

Faturamento Consolidado da AWS mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Com múltiplas contas, a organização centraliza cobrança e visualização financeira.

Isso facilita governança e pode ajudar em descontos baseados em volume.

---

## Por que existe

* visão consolidada de custos;
* pagamento centralizado;
* análise por conta vinculada;
* possível agregação de descontos em certos contextos;
* governança financeira multi-conta.

---

## Como funciona

O funcionamento depende de medição de uso, cobrança, categorização, alertas, relatórios, planos e decisões de operação. Ao estudar Faturamento Consolidado da AWS, relacione sempre consumo técnico com impacto financeiro.

---

## Exemplo prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Diferenças importantes

**Pontos que Costumam Gerar Confusão**

Uma vantagem do faturamento consolidado é a possibilidade de qualificação para preços por volume, porque o uso pode ser agregado entre contas da organização.

---

## Cuidados

Consolidar fatura não substitui tags, categorias e budgets.

A organização ainda precisa saber qual conta, projeto ou time gerou cada custo.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Faturamento consolidado não elimina necessidade de tags.

Também não cria permissões compartilhadas automaticamente.

---

## Relação com outras notas

**Relação com Contas**

Ambientes profissionais raramente usam uma única conta.

É comum separar produção, desenvolvimento, segurança, logs, sandbox e workloads.

Faturamento consolidado ajuda a enxergar tudo junto sem perder separação de contas.

- [[AWS Organizations]]
- [[AWS Cost Explorer]]
- [[AWS Budgets]]
- [[AWS Billing and Cost Management]]
- [[AWS Trusted Advisor]]
