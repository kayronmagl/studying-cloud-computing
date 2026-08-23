O Modelo de Precificação da AWS é baseado principalmente em consumo.

A AWS permite criar recursos sob demanda e pagar conforme uso, combinando tempo, volume, requisições, transferência, armazenamento, capacidade provisionada e recursos adicionais.

Modelo de Precificação da AWS mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

Modelo de Precificação da AWS deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

Na AWS, custo depende de uso, região, serviço, armazenamento, requisições, tráfego, logs, suporte e compromissos de uso.

---

## Por que existe

Modelo de Precificação da AWS existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

**Pay-as-you-go**

O conceito de [[Pay-as-you-go]] significa pagar pelo que usa.

Isso reduz necessidade de [[CapEx (Capital Expenditures)]] e desloca custo para [[OpEx (Operating Expenses)]].

**Variáveis de Custo**

Custos podem depender de:

* região;
* tempo ligado;
* quantidade de requisições;
* volume armazenado;
* transferência de dados;
* IOPS;
* throughput;
* logs;
* backups;
* snapshots;
* suporte;
* compromissos de uso.

**Não é Automaticamente Barato**

Nuvem reduz desperdício quando bem usada.

Mas recursos esquecidos, superdimensionados ou mal arquitetados podem custar caro.

**Conclusão**

Entender preço na AWS exige entender arquitetura.

Custo não é uma tabela isolada. É consequência do desenho técnico.

**Primeiro contato com custos**

[[AWS Free Tier]] ajuda no primeiro contato com a AWS, mas não elimina a necessidade de entender cobrança, limites e consumo real.

---

## Exemplo prático

Uma instância [[Amazon EC2|EC2]] parada pode não cobrar computação, mas volumes [[Amazon EBS]], snapshots, IPs elásticos não usados e logs podem continuar gerando custo.

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Diferenças importantes

**Como Diferenciar**

* Pricing Calculator estima custo antes.
* Cost Explorer analisa custo real.
* Budgets alerta sobre limites.
* Tags ajudam alocação de custo.
* Trusted Advisor recomenda melhorias.
* Support Plans mudam nível de suporte.

---

## Cuidados

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

Pay-as-you-go não significa barato. Significa pagar conforme uso. Uso sem controle pode ficar caro.

---

## Relação com outras notas

- [[Pay-as-you-go]]
- [[CapEx (Capital Expenditures)]]
- [[OpEx (Operating Expenses)]]
- [[AWS Free Tier]]
- [[Amazon EBS]]
- [[AWS Cost Explorer]]
- [[AWS Budgets]]
- [[AWS Billing and Cost Management]]
- [[AWS Trusted Advisor]]
