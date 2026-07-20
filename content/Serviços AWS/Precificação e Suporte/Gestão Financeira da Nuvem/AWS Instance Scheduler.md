AWS Instance Scheduler é uma solução usada para iniciar e parar recursos conforme agenda.

Ela ajuda a reduzir custo de ambientes que não precisam ficar ligados continuamente.

---

## Visão geral

AWS Instance Scheduler mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Exemplo

Ambientes de desenvolvimento podem desligar à noite e ligar no início do expediente.


* segunda a sexta: ligar 08:00.
* desligar 19:00


---

## Relação com Elasticidade

Instance Scheduler aparece como ferramenta de elasticidade financeira: adequa uso ao padrão esperado.

Ela não substitui [[Amazon EC2 Auto Scaling]], mas complementa workloads previsíveis.

---

## Onde Ajuda

* desenvolvimento;
* testes;
* homologação;
* laboratórios;
* ambientes sazonais;
* máquinas administrativas.

---

## Cuidado

Não use agendamento cego em produção crítica.

Antes de desligar recursos, entenda dependências e impacto.

---

## Exemplo Prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Cuidados importantes

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.
