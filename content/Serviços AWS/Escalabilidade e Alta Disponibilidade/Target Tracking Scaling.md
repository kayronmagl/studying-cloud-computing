Target Tracking Scaling é uma política de escala que tenta manter uma métrica próxima de um valor alvo.

É uma das formas mais simples de configurar Auto Scaling.


Target Tracking Scaling ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Exemplo

* manter CPU média em 50%


Se CPU passa do alvo, o grupo escala para fora.

Se CPU fica abaixo, o grupo pode escalar para dentro.

---

## Vantagem

É fácil de entender porque funciona como um termostato.

O sistema ajusta capacidade para manter a métrica perto do alvo.

---

## Métricas

Pode usar métricas como:

* CPU;
* requisições por target;
* métricas customizadas;
* outras métricas compatíveis.

---

## Cuidado

Escolha uma métrica proporcional à carga.

Se a métrica não muda de forma previsível com demanda, o scaling será ruim.

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

---

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
