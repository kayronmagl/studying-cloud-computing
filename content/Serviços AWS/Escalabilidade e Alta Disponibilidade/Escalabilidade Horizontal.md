Escalabilidade Horizontal significa adicionar mais recursos em paralelo.

Exemplo: em vez de uma instância maior, usar várias instâncias atrás de um load balancer.

---

## Visão geral

Escalabilidade Horizontal ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Exemplo AWS

Uma aplicação web usa:

* múltiplas instâncias [[Amazon EC2]];
* [[Auto Scaling Groups]];
* [[Application Load Balancer]];
* múltiplas [[Availability Zones (AZ)]].

---

## Vantagens

* reduz dependência de uma máquina única;
* melhora disponibilidade;
* permite crescimento gradual;
* combina bem com Auto Scaling;
* permite substituição de instâncias com falha.

---

## Requisitos

A aplicação precisa evitar estado local.

Sessões devem ir para banco, cache, token ou serviço compartilhado. Arquivos devem ir para [[Amazon S3]] ou [[Amazon EFS]].

---

## Cuidado

Escalar horizontalmente a camada web não resolve gargalo no banco.

A arquitetura inteira precisa ser analisada.

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
