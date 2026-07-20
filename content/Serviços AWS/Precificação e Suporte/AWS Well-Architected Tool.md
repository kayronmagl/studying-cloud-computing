AWS Well-Architected Tool é a ferramenta da AWS para realizar revisões baseadas no [[AWS Well-Architected Framework]].

Ela ajuda a documentar workloads, responder perguntas por pilar e identificar riscos.

---

## Visão geral

AWS Well-Architected Tool mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Uso

A equipe registra um workload e avalia perguntas sobre operação, segurança, confiabilidade, performance, custo e sustentabilidade.

---

## Resultado

A ferramenta ajuda a identificar riscos e sugestões de melhoria.

---

## Relação com Precificação

No pilar de custo, a revisão pode apontar desperdícios, falta de tags, ausência de budgets, superdimensionamento e uso inadequado de modelos de compra.

---

## Cuidado

Responder perguntas sem agir não melhora arquitetura.

A ferramenta deve gerar plano de melhoria.

---

## Exemplo Prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Cuidados importantes

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.
