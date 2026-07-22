Scheduled Scaling é uma forma de escala programada em que a capacidade muda em horários definidos.

Ela é usada quando a demanda é previsível.


Scheduled Scaling ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Exemplo

Uma empresa sabe que seu sistema recebe mais tráfego às 8h.

Ela pode configurar o [[Amazon EC2 Auto Scaling]] para aumentar capacidade às 7h45 e reduzir capacidade depois do pico.


* 07:45: aumentar capacidade desejada para 8.
* 18:30: reduzir capacidade desejada para 3.


---

## Diferença para Escala Reativa

Escala reativa responde a métricas.

Scheduled scaling age antes do pico.

Isso é útil quando a aplicação demora para inicializar ou quando o tráfego previsível começa rapidamente.

---

## Quando Usar

Use para:

* horário comercial;
* eventos planejados;
* campanhas;
* aulas online;
* processamento noturno;
* rotinas de fechamento;
* datas sazonais;
* cargas previsíveis.

---

## Relação com CloudWatch

Mesmo usando agendamento, [[Amazon CloudWatch]] continua importante.

A agenda cobre o padrão esperado. Métricas e alarmes cobrem variações inesperadas.

---

## Cuidado

Scheduled scaling não substitui políticas dinâmicas.

Se a demanda real for maior que a previsão, a aplicação ainda precisa de [[Target Tracking Scaling]], [[Step Scaling]] ou outra política baseada em métricas.

Também é importante revisar fusos horários, recorrência, janelas de manutenção e eventos especiais.

---

## Exemplo Prático

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Cuidados importantes

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

## Como entender isso

Este conceito pertence ao módulo de escalabilidade e alta disponibilidade.

## Ponto central

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

## Como Diferenciar

* CloudWatch observa.
* Auto Scaling ajusta capacidade.
* ELB distribui tráfego.
* Health checks removem destinos ruins.
* Multi-AZ reduz falha zonal.
* RTO e RPO guiam recuperação.

## Cuidado importante

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.
