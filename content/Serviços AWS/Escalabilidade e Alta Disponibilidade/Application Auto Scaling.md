Application Auto Scaling é o serviço da AWS usado para configurar escala automática em recursos além de instâncias EC2.

Enquanto [[Amazon EC2 Auto Scaling]] gerencia instâncias [[Amazon EC2]], Application Auto Scaling pode ajustar capacidade de outros serviços compatíveis.


Application Auto Scaling ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Por que Existe

Arquiteturas modernas não escalam apenas servidores.

Uma aplicação pode usar:

* containers;
* tabelas NoSQL;
* réplicas de banco;
* filas;
* serviços gerenciados;
* workers;
* funções serverless.

Se apenas a camada web escala, o gargalo pode migrar para outra camada.

---

## Exemplos

Application Auto Scaling pode ser usado com serviços como:

* [[Amazon ECS]];
* [[Amazon DynamoDB]];
* réplicas do [[Amazon Aurora]] em certos cenários;
* outros recursos escaláveis suportados pela AWS.

---

## Relação com CloudWatch

Application Auto Scaling usa métricas, alvos e políticas de escala.

Assim como em EC2 Auto Scaling, [[Amazon CloudWatch]] fornece sinais para decisões.

---

## Exemplo

Uma aplicação usa ECS para processar pedidos.

Quando o número de mensagens na fila [[Amazon SQS]] cresce, Application Auto Scaling aumenta a quantidade de tasks ECS.

Quando a fila esvazia, reduz capacidade.

---

## Cuidado

Escalar um serviço isolado não garante saúde do sistema inteiro.

A escala precisa considerar dependências como banco, APIs externas, limites de conta e custo.

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
