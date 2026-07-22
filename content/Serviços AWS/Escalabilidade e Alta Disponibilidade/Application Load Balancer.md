Application Load Balancer, ou ALB, é um tipo de load balancer da AWS para tráfego HTTP e HTTPS na camada de aplicação.

Ele é usado em aplicações web, APIs e arquiteturas baseadas em rotas.


Application Load Balancer ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Características

ALB pode rotear por:

* host;
* path;
* headers;
* método HTTP;
* query string;
* regras de listener.

---

## Target Groups

ALB envia tráfego para [[Target Groups]].

Cada target group possui destinos e health checks.

---

## Uso

* aplicações web;
* APIs;
* microsserviços;
* roteamento por path;
* integração com containers;
* TLS termination;
* autenticação em alguns cenários.

---

## Relação com Auto Scaling

Um [[Auto Scaling Groups|Auto Scaling Group]] pode registrar instâncias em target groups usados por ALB.

---

## Cuidado

ALB trabalha na camada de aplicação.

Para tráfego TCP/UDP de alta performance, [[Network Load Balancer]] pode ser mais adequado.

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
