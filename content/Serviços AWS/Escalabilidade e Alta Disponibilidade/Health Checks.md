Health Checks são verificações usadas para determinar se um recurso está saudável.

Eles são essenciais para [[Alta Disponibilidade]], [[Elastic Load Balancing]] e [[Amazon EC2 Auto Scaling]].

---

## Visão geral

Health Checks ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Como Funcionam

Um health check pode testar:

* resposta HTTP;
* porta TCP;
* endpoint específico;
* status de instância;
* disponibilidade de serviço.

Se o recurso falha no health check, ele pode ser removido da rotação ou substituído.

---

## Load Balancer

Load balancers usam health checks para evitar enviar tráfego a targets com falha.

---

## Auto Scaling

Auto Scaling pode substituir instâncias consideradas não saudáveis.

---

## Boa Prática

Health checks devem testar saúde real da aplicação.

Um endpoint que responde `200 OK` mesmo quando banco está fora pode dar falsa sensação de saúde.

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
