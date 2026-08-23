Graceful Degradation é a capacidade de um sistema continuar oferecendo funcionalidade reduzida quando uma dependência falha.

Em vez de cair completamente, ele degrada de forma controlada.

Graceful Degradation ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Graceful Degradation pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Graceful Degradation existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Estratégias**

* fallback;
* cache;
* respostas parciais;
* filas;
* modo somente leitura;
* degradação de recursos não críticos;
* mensagens claras ao usuário.

---

## Exemplo prático

Uma loja virtual perde o serviço de recomendação.

Em vez de derrubar a página, mostra produtos populares ou oculta recomendações.

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

Degradação precisa ser planejada antes do incidente.

Improvisar durante falha costuma gerar comportamento inconsistente.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com Alta Disponibilidade**

Alta disponibilidade não significa que todas as funcionalidades precisam estar perfeitas o tempo todo.

Às vezes, manter o fluxo principal ativo é mais importante do que manter recursos secundários.

**Relação com AWS**

Pode usar [[Amazon CloudWatch]] para detectar falha, [[Amazon SQS]] para segurar trabalho e caches para manter respostas parciais.
