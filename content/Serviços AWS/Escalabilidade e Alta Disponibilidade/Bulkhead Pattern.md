Bulkhead Pattern é um padrão de resiliência que isola recursos para evitar que uma falha consuma o sistema inteiro.

O nome vem de compartimentos estanques de navios: se um compartimento alaga, o navio não afunda inteiro.


Bulkhead Pattern ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Aplicação em Software

Uma aplicação pode separar pools de conexão, filas, workers ou limites por tipo de operação.

Se um módulo falha, não consome todos os recursos dos outros.

---

## Exemplo

Um sistema separa workers de pagamento e workers de e-mail.

Se envio de e-mail trava, processamento de pagamento continua.

---

## Relação com AWS

Pode ser implementado com:

* filas [[Amazon SQS]] separadas;
* funções [[AWS Lambda]] separadas;
* Auto Scaling Groups distintos;
* target groups diferentes;
* limites de concorrência;
* contas separadas.

---

## Cuidado

Isolamento aumenta complexidade, mas reduz falhas em cascata.

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
