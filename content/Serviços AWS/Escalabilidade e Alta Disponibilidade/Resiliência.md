Resiliência é a capacidade de um workload se recuperar de falhas, adaptar-se a mudanças de demanda e continuar entregando sua função.

Ela inclui disponibilidade, recuperação, elasticidade, tolerância a falhas e operação observável.

Resiliência ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Resiliência pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

---

## Por que existe

Resiliência existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Componentes**

Resiliência envolve:

* [[Alta Disponibilidade]];
* [[Tolerância a Falhas]];
* [[Disaster Recovery (DR)]];
* [[Failover]];
* backups;
* replicação;
* health checks;
* automação;
* observabilidade com [[Amazon CloudWatch]].

**Testando falhas de forma controlada**

[[AWS Fault Injection Service (FIS)]] entra quando a equipe quer testar como a arquitetura se comporta diante de falhas planejadas.

---

## Exemplo prático

Uma aplicação resiliente detecta uma instância com falha, remove do load balancer, cria outra instância e continua atendendo usuários.

Isso exige integração entre [[Elastic Load Balancing]], [[Health Checks]] e [[Amazon EC2 Auto Scaling]].

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Diferenças importantes

**Diferença para Disponibilidade**

Disponibilidade mede se o sistema está operacional.

Resiliência inclui a capacidade de se recuperar quando algo dá errado.

---

## Cuidados

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

---

## Relação com outras notas

- [[Alta Disponibilidade]]
- [[Tolerância a Falhas]]
- [[Disaster Recovery (DR)]]
- [[Failover]]
- [[Amazon CloudWatch]]
- [[AWS Fault Injection Service (FIS)]]
- [[Elastic Load Balancing]]
- [[Health Checks]]
- [[Amazon EC2 Auto Scaling]]
- [[Availability Zones (AZ)]]
