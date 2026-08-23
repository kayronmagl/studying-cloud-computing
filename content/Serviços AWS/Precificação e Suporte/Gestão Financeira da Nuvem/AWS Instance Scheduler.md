AWS Instance Scheduler é uma solução usada para iniciar e parar recursos conforme agenda.

Ela ajuda a reduzir custo de ambientes que não precisam ficar ligados continuamente.

AWS Instance Scheduler mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.

---

## O que é

AWS Instance Scheduler deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

---

## Por que existe

AWS Instance Scheduler existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

**Onde Ajuda**

* desenvolvimento;
* testes;
* homologação;
* laboratórios;
* ambientes sazonais;
* máquinas administrativas.

---

## Exemplo prático

Ambientes de desenvolvimento podem desligar à noite e ligar no início do expediente.

* segunda a sexta: ligar 08:00.
* desligar 19:00

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Diferenças importantes

Não confunda reduzir custo com comprometer qualidade. Uma economia pode ser ruim se diminuir disponibilidade, segurança, recuperação ou desempenho além do aceitável.

---

## Cuidados

Não use agendamento cego em produção crítica.

Antes de desligar recursos, entenda dependências e impacto.

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

---

## Relação com outras notas

**Relação com Elasticidade**

Instance Scheduler aparece como ferramenta de elasticidade financeira: adequa uso ao padrão esperado.

Ela não substitui [[Amazon EC2 Auto Scaling]], mas complementa workloads previsíveis.
