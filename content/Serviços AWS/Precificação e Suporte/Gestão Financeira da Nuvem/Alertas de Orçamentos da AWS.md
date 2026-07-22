Alertas de Orçamentos da AWS são notificações associadas a [[AWS Budgets]].

Eles avisam quando custo ou uso real, previsto ou configurado atinge limites definidos.


Alertas de Orçamentos da AWS mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Canais

Alertas podem ser enviados para e-mail e integrados a mecanismos como [[Amazon SNS]], dependendo da configuração.

Isso permite notificar pessoas ou sistemas.

---

## Exemplo

* quando custo previsto atingir 80% do orçamento: enviar alerta para equipe.
* quando custo real atingir 100%: notificar responsável financeiro.


---

## Uso

Alertas ajudam a detectar problema antes do fechamento da fatura.

Eles são essenciais em ambientes de estudo, contas compartilhadas e produção.

---

## Cuidado

Alertas precisam ter dono.

Se todos recebem e ninguém age, o alerta não controla custo.

---

## Exemplo Prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Cuidados importantes

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.
