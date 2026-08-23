[[AWS WAF|WAF]] filtra tráfego HTTP/HTTPS para bloquear padrões maliciosos. Na AWS, [[AWS WAF]] protege CloudFront, load balancers e [[APIs|APIs]].

---

## O que é

[[AWS WAF]] é o firewall de aplicação web da AWS.

Ele filtra requisições HTTP/HTTPS antes que cheguem à aplicação.

---

## Por que existe

* SQL injection;
* XSS;
* bots simples;
* padrões maliciosos;
* abuso por IP;
* requisições fora do padrão.

---

## Como funciona

**Onde Pode Ser Usado**

* CloudFront;
* Application Load Balancer;
* [[APIs|API]] Gateway;
* AppSync.

---

## Exemplo prático

Quando um usuário acessa uma aplicação hospedada na AWS, a requisição pode passar pela internet pública, por redes de telecomunicação, por edge locations, por uma CDN, por um load balancer e finalmente por recursos dentro de uma [[Amazon VPC|VPC]].

Cada etapa pode melhorar ou piorar a experiência.

Uma aplicação pode usar CloudFront para reduzir latência, WAF para filtrar tráfego malicioso e Route 53 para direcionar usuários ao endpoint adequado.

Sem esses componentes, todo tráfego pode depender diretamente de uma origem distante e mais sensível a picos.

---

## Diferenças importantes

Compare WAF (Web Application Firewall) com região, edge, CDN, DNS, cache e roteamento. CDN entrega conteúdo; DNS resolve nomes; cache guarda cópias; roteamento decide caminhos; região executa serviços principais.

---

## Cuidados

Problemas de rede nem sempre aparecem como “rede fora”. Muitas vezes aparecem como latência alta, timeout, perda de pacotes, gargalo de throughput, cache mal configurado ou custo de transferência inesperado.

Por isso, entender este conceito ajuda a interpretar desempenho e disponibilidade de aplicações em nuvem.

Problemas de rede aparecem como lentidão, timeouts, custo alto, cache errado ou indisponibilidade parcial.

Por isso, rede global precisa ser observada com métricas e logs.

WAF não substitui segurança da aplicação. Ele filtra tráfego, mas código vulnerável continua precisando ser corrigido.

---

## Relação com outras notas

- [[AWS WAF]]
