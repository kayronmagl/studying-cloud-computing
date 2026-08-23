Elastic Load Balancing, ou ELB, é o serviço da AWS que distribui tráfego entre múltiplos destinos saudáveis.

Ele é essencial para [[Escalabilidade Horizontal]] e [[Alta Disponibilidade]].

Elastic Load Balancing ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Elastic Load Balancing distribui tráfego entre destinos saudáveis.

Ele melhora disponibilidade e permite escala horizontal.

---

## Por que existe

Elastic Load Balancing existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

Um load balancer recebe tráfego de clientes e encaminha para destinos registrados.

Destinos podem incluir:

* instâncias [[Amazon EC2]];
* containers;
* endereços IP;
* funções [[AWS Lambda|Lambda]], em alguns tipos de integração.

O load balancer usa [[Health Checks]] para enviar tráfego apenas a destinos saudáveis.

**Tipos**

Os principais tipos são:

* [[Application Load Balancer]];
* [[Network Load Balancer]];
* [[Gateway Load Balancer]];
* Classic Load Balancer, legado.

**Multi-AZ**

Load balancers podem operar em múltiplas [[Availability Zones (AZ)]], ajudando a reduzir impacto de falhas zonais.

**Tipos na prática**

* Application Load Balancer: HTTP/HTTPS, camada 7.
* Network Load Balancer: TCP/UDP/TLS, camada 4, alta performance.
* Gateway Load Balancer: appliances virtuais de rede.

**Como Funciona na prática**

O load balancer recebe requisições e envia para targets em target groups. Health checks definem quais targets estão saudáveis.

---

## Exemplo prático

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Diferenças importantes

Não confunda escalabilidade, disponibilidade e resiliência. Escalabilidade lida com variação de demanda, disponibilidade lida com acesso contínuo e resiliência lida com sobreviver e recuperar após falhas.

---

## Cuidados

Load balancer não corrige aplicação quebrada.

Ele só distribui tráfego. A aplicação precisa responder corretamente e expor health checks confiáveis.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Load balancer não corrige aplicação ruim. Ele apenas evita enviar tráfego para destinos marcados como não saudáveis.

---

## Relação com outras notas

**Relação com Auto Scaling**

Com [[Amazon EC2 Auto Scaling]], novas instâncias podem ser registradas automaticamente em [[Target Groups]].

Quando ficam saudáveis, passam a receber tráfego.

**Relação com Auto Scaling na prática**

Novas instâncias criadas por Auto Scaling podem entrar no target group e passar a receber tráfego.
