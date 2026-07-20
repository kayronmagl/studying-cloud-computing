[[AWS WAF|WAF]] filtra tráfego HTTP/HTTPS para bloquear padrões maliciosos. Na AWS, [[AWS WAF]] protege CloudFront, load balancers e APIs.

---

## Visão geral

WAF (Web Application Firewall) ajuda a entender o caminho dos dados. Em nuvem, desempenho e disponibilidade dependem muito de como o tráfego sai do usuário, passa pela rede e chega ao serviço.

Sempre associe este conceito a latência, roteamento, cache, segurança ou entrega de conteúdo.

---

## Exemplo Prático

Quando um usuário acessa uma aplicação hospedada na AWS, a requisição pode passar pela internet pública, por redes de telecomunicação, por edge locations, por uma CDN, por um load balancer e finalmente por recursos dentro de uma VPC.

Cada etapa pode melhorar ou piorar a experiência.

---

## Cuidados importantes

Problemas de rede nem sempre aparecem como “rede fora”. Muitas vezes aparecem como latência alta, timeout, perda de pacotes, gargalo de throughput, cache mal configurado ou custo de transferência inesperado.

Por isso, entender este conceito ajuda a interpretar desempenho e disponibilidade de aplicações em nuvem.

---

## Exemplo Arquitetural

Uma aplicação pode usar CloudFront para reduzir latência, WAF para filtrar tráfego malicioso e Route 53 para direcionar usuários ao endpoint adequado.

Sem esses componentes, todo tráfego pode depender diretamente de uma origem distante e mais sensível a picos.

---

## Cuidado adicional

Problemas de rede aparecem como lentidão, timeouts, custo alto, cache errado ou indisponibilidade parcial.

Por isso, rede global precisa ser observada com métricas e logs.

## Explicação principal

[[AWS WAF]] é o firewall de aplicação web da AWS.

Ele filtra requisições HTTP/HTTPS antes que cheguem à aplicação.

## Protege Contra

* SQL injection;
* XSS;
* bots simples;
* padrões maliciosos;
* abuso por IP;
* requisições fora do padrão.

## Onde Pode Ser Usado

* CloudFront;
* Application Load Balancer;
* API Gateway;
* AppSync.

## Cuidado importante

WAF não substitui segurança da aplicação. Ele filtra tráfego, mas código vulnerável continua precisando ser corrigido.
