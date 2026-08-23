Health Checks são verificações usadas para determinar se um recurso está saudável.

Eles são essenciais para [[Alta Disponibilidade]], [[Elastic Load Balancing]] e [[Amazon EC2 Auto Scaling]].

Health Checks ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Health Checks pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Health Checks existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Como Funcionam**

Um health check pode testar:

* resposta HTTP;
* porta TCP;
* endpoint específico;
* status de instância;
* disponibilidade de serviço.

Se o recurso falha no health check, ele pode ser removido da rotação ou substituído.

**Load Balancer**

Load balancers usam health checks para evitar enviar tráfego a targets com falha.

**Auto Scaling**

Auto Scaling pode substituir instâncias consideradas não saudáveis.

---

## Exemplo prático

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Diferenças importantes

**Como Diferenciar**

* CloudWatch observa.
* Auto Scaling ajusta capacidade.
* ELB distribui tráfego.
* Health checks removem destinos ruins.
* Multi-AZ reduz falha zonal.
* RTO e RPO guiam recuperação.

---

## Cuidados

**Boa Prática**

Health checks devem testar saúde real da aplicação.

Um endpoint que responde `200 OK` mesmo quando banco está fora pode dar falsa sensação de saúde.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

- [[Alta Disponibilidade]]
- [[Elastic Load Balancing]]
- [[Amazon EC2 Auto Scaling]]
- [[Availability Zones (AZ)]]
- [[Application Load Balancer]]
- [[Amazon CloudWatch]]
