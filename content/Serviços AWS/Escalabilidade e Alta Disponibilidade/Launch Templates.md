Launch Templates definem como uma instância [[Amazon EC2]] deve ser criada.

Eles são usados por [[Auto Scaling Groups]] para lançar novas instâncias de forma padronizada.


Launch Templates ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Conteúdo

Um launch template pode definir:

* [[Amazon Machine Image (AMI)]];
* tipo de instância;
* key pair;
* security groups;
* IAM instance profile;
* user data;
* volumes;
* tags;
* configurações de rede.

---

## Por que Importa

Sem template, cada instância poderia ser criada de forma diferente.

Com template, o Auto Scaling consegue recriar capacidade automaticamente.

---

## Versionamento

Launch Templates podem ter versões.

Isso permite atualizar configuração com controle.

---

## Relação com Deploy

Uma nova versão de aplicação pode ser embutida em nova AMI ou user data, dependendo da estratégia.

---

## Cuidado

Se o template estiver errado, o Auto Scaling criará instâncias erradas repetidamente.

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
