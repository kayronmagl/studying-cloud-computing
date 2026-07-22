AWS Cost Categories permite criar agrupamentos personalizados de custo na AWS.

Ele ajuda a organizar custos em dimensões de negócio, mesmo quando tags e contas não são suficientes.


AWS Cost Categories mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Por que Usar

Empresas podem querer agrupar custos por:

* produto;
* unidade de negócio;
* centro de custo;
* ambiente;
* plataforma;
* cliente;
* área interna.

---

## Diferença para Tags

[[Cost Allocation Tags]] são aplicadas em recursos.

Cost Categories cria regras de categorização em nível de billing, combinando contas, tags, serviços e outros critérios.

---

## Exemplo

Uma organização pode criar categoria:


* Produto A: contas 1 e 2.
* tags Project: A.
* Produto B: conta 3.
* tags Project: B.


---

## Cuidado

Categorias precisam acompanhar mudanças organizacionais.

Se regras ficam antigas, relatórios financeiros ficam distorcidos.

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
