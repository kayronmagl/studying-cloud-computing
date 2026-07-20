Resiliência é a capacidade de um workload se recuperar de falhas, adaptar-se a mudanças de demanda e continuar entregando sua função.

Ela inclui disponibilidade, recuperação, elasticidade, tolerância a falhas e operação observável.

---

## Visão geral

Resiliência ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Componentes

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

---

## Diferença para Disponibilidade

Disponibilidade mede se o sistema está operacional.

Resiliência inclui a capacidade de se recuperar quando algo dá errado.

---

## Exemplo

Uma aplicação resiliente detecta uma instância com falha, remove do load balancer, cria outra instância e continua atendendo usuários.

Isso exige integração entre [[Elastic Load Balancing]], [[Health Checks]] e [[Amazon EC2 Auto Scaling]].

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

## Testando falhas de forma controlada

[[AWS Fault Injection Service (FIS)]] entra quando a equipe quer testar como a arquitetura se comporta diante de falhas planejadas.
