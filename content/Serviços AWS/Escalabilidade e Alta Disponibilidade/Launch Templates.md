Launch Templates definem como uma instância [[Amazon EC2]] deve ser criada.

Eles são usados por [[Auto Scaling Groups]] para lançar novas instâncias de forma padronizada.

Launch Templates ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Launch Templates pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Sem template, cada instância poderia ser criada de forma diferente.

Com template, o Auto Scaling consegue recriar capacidade automaticamente.

---

## Como funciona

**Conteúdo**

Um launch template pode definir:

* [[Amazon Machine Image (AMI)]];
* tipo de instância;
* key pair;
* security groups;
* [[AWS Identity and Access Management (IAM)|IAM]] instance profile;
* user data;
* volumes;
* tags;
* configurações de rede.

**Versionamento**

Launch Templates podem ter versões.

Isso permite atualizar configuração com controle.

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

Se o template estiver errado, o Auto Scaling criará instâncias erradas repetidamente.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com Deploy**

Uma nova versão de aplicação pode ser embutida em nova AMI ou user data, dependendo da estratégia.

- [[Amazon EC2]]
- [[Auto Scaling Groups]]
- [[Amazon Machine Image (AMI)]]
- [[Availability Zones (AZ)]]
- [[Application Load Balancer]]
- [[Amazon EC2 Auto Scaling]]
- [[Amazon CloudWatch]]
