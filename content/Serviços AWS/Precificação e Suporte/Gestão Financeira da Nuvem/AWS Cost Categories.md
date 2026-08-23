AWS Cost Categories permite criar agrupamentos personalizados de custo na AWS.

Ele ajuda a organizar custos em dimensões de negócio, mesmo quando tags e contas não são suficientes.

AWS Cost Categories mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

AWS Cost Categories deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

Na AWS, custo depende de uso, região, serviço, armazenamento, requisições, tráfego, logs, suporte e compromissos de uso.

---

## Por que existe

Empresas podem querer agrupar custos por:

* produto;
* unidade de negócio;
* centro de custo;
* ambiente;
* plataforma;
* cliente;
* área interna.

---

## Como funciona

O funcionamento depende de medição de uso, cobrança, categorização, alertas, relatórios, planos e decisões de operação. Ao estudar AWS Cost Categories, relacione sempre consumo técnico com impacto financeiro.

---

## Exemplo prático

Uma organização pode criar categoria:

* Produto A: contas 1 e 2.
* tags Project: A.
* Produto B: conta 3.
* tags Project: B.

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Diferenças importantes

**Diferença para Tags**

[[Cost Allocation Tags]] são aplicadas em recursos.

Cost Categories cria regras de categorização em nível de billing, combinando contas, tags, serviços e outros critérios.

**Como Diferenciar**

* Pricing Calculator estima custo antes.
* Cost Explorer analisa custo real.
* Budgets alerta sobre limites.
* Tags ajudam alocação de custo.
* Trusted Advisor recomenda melhorias.
* Support Plans mudam nível de suporte.

---

## Cuidados

Categorias precisam acompanhar mudanças organizacionais.

Se regras ficam antigas, relatórios financeiros ficam distorcidos.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Pay-as-you-go não significa barato. Significa pagar conforme uso. Uso sem controle pode ficar caro.

---

## Relação com outras notas

- [[AWS Cost Explorer]]
- [[AWS Budgets]]
- [[AWS Billing and Cost Management]]
- [[AWS Trusted Advisor]]
- [[Cost Allocation Tags]]
