Graceful Degradation é a capacidade de um sistema continuar oferecendo funcionalidade reduzida quando uma dependência falha.

Em vez de cair completamente, ele degrada de forma controlada.

---

## Visão geral

Graceful Degradation ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Exemplo

Uma loja virtual perde o serviço de recomendação.

Em vez de derrubar a página, mostra produtos populares ou oculta recomendações.

---

## Relação com Alta Disponibilidade

Alta disponibilidade não significa que todas as funcionalidades precisam estar perfeitas o tempo todo.

Às vezes, manter o fluxo principal ativo é mais importante do que manter recursos secundários.

---

## Estratégias

* fallback;
* cache;
* respostas parciais;
* filas;
* modo somente leitura;
* degradação de recursos não críticos;
* mensagens claras ao usuário.

---

## Relação com AWS

Pode usar [[Amazon CloudWatch]] para detectar falha, [[Amazon SQS]] para segurar trabalho e caches para manter respostas parciais.

---

## Cuidado

Degradação precisa ser planejada antes do incidente.

Improvisar durante falha costuma gerar comportamento inconsistente.

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
