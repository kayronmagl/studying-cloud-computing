Logs do Amazon CloudWatch centralizam logs de aplicações, serviços e infraestrutura.

Logs são registros de eventos. Eles ajudam a explicar por que algo aconteceu.

Logs do Amazon CloudWatch ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Logs do Amazon CloudWatch pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Logs do Amazon CloudWatch existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Fontes**

Logs podem vir de:

* [[AWS Lambda]];
* instâncias [[Amazon EC2]];
* containers;
* aplicações;
* [[Amazon API Gateway]];
* [[Amazon VPC|VPC]] Flow Logs;
* serviços integrados.

**Log Groups e Log Streams**

Um log group organiza logs por aplicação, serviço ou recurso.

Um log stream representa uma sequência de eventos dentro do grupo.

**Uso**

Logs ajudam a investigar:

* erros;
* exceções;
* timeouts;
* falhas de autenticação;
* problemas de dependência;
* comportamento anormal;
* eventos de deploy.

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

Logs podem conter dados sensíveis.

Não registre senhas, tokens, chaves ou dados pessoais sem necessidade.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com Métricas**

Métricas mostram que algo está errado.

Logs ajudam a entender por quê.

- [[AWS Lambda]]
- [[Amazon EC2]]
- [[Amazon API Gateway]]
- [[Availability Zones (AZ)]]
- [[Application Load Balancer]]
- [[Amazon EC2 Auto Scaling]]
- [[Amazon CloudWatch]]
