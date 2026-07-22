Amazon DynamoDB sob Demanda é o modo de capacidade em que o [[Amazon DynamoDB]] ajusta automaticamente a capacidade de leitura e escrita conforme o tráfego.

Ele é útil quando o padrão de acesso é imprevisível.


Amazon DynamoDB sob Demanda mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Diferença para Capacidade Provisionada

Na capacidade provisionada, a equipe define unidades de leitura e escrita.

No modo sob demanda, o serviço lida com variação de tráfego sem planejamento manual de throughput.

---

## Quando Usar

Use quando:

* tráfego é irregular;
* aplicação é nova;
* não há histórico de uso;
* picos são imprevisíveis;
* simplicidade operacional é prioridade.

---

## Relação com Custo

Sob demanda pode ser mais simples e adequado para tráfego variável.

Para cargas muito previsíveis e constantes, capacidade provisionada com ajuste correto pode ser avaliada.

---

## Cuidado

Simplicidade não elimina necessidade de monitorar custos.

Picos de tráfego ainda podem gerar aumento de cobrança.

---

## Exemplo Prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Cuidados importantes

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.
