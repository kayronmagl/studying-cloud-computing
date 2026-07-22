Amazon EC2 Auto Scaling é o serviço que ajusta automaticamente a quantidade de instâncias [[Amazon EC2]] disponíveis para uma aplicação.

Ele ajuda a manter capacidade suficiente para atender demanda e pode substituir instâncias com falha.


Amazon EC2 Auto Scaling ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Ideia Central

O serviço trabalha com [[Auto Scaling Groups]].

Um grupo define:

* capacidade mínima;
* capacidade desejada;
* capacidade máxima;
* sub-redes;
* template de lançamento;
* políticas de escala;
* health checks;
* integração com load balancers.

---

## Como Funciona

Fluxo comum:


* CloudWatch observa métrica: ↓.
* alarme ou política detecta necessidade: ↓.
* Auto Scaling ajusta capacidade: ↓.
* novas instâncias são lançadas: ↓.
* health checks validam: ↓.
* load balancer recebe destinos saudáveis


---

## Substituição de Instâncias

Auto Scaling também ajuda a manter disponibilidade.

Se uma instância falha em health check, o grupo pode terminar essa instância e lançar outra.

---

## Relação com ELB

Com [[Elastic Load Balancing]], novas instâncias entram no target group e passam a receber tráfego quando saudáveis.

---

## Tipos de Escala

* [[Target Tracking Scaling]];
* [[Step Scaling]];
* [[Scheduled Scaling]];
* escala manual;
* escala baseada em métricas customizadas.

---

## Cuidado

Auto Scaling não resolve aplicação stateful mal desenhada.

Se o estado fica preso na instância, remover ou substituir instâncias pode causar perda de sessão ou inconsistência.

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

## Explicação principal

Amazon EC2 Auto Scaling ajusta automaticamente a quantidade de instâncias EC2.

Ele usa Auto Scaling Groups, launch templates, health checks e políticas de escala.

## Como Funciona na prática

O grupo possui mínimo, desejado e máximo.

Quando a demanda aumenta, o grupo pode lançar instâncias. Quando cai, pode remover. Se uma instância falha, pode substituí-la.

## Tipos de Escala na prática

* Target Tracking;
* Step Scaling;
* Scheduled Scaling;
* escala manual.

## Relação com CloudWatch

Métricas e alarmes do CloudWatch podem acionar políticas de escala.

## Cuidado importante

Auto Scaling não distribui tráfego. Quem distribui é o Elastic Load Balancing. Auto Scaling ajusta capacidade.

---

## Regras de escala

O Auto Scaling usa [[Scaling Policies]] para decidir quando aumentar ou reduzir capacidade.
