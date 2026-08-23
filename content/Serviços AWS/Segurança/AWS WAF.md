AWS WAF é o Web Application Firewall da AWS.

Ele permite monitorar, permitir, bloquear ou desafiar requisições HTTP e HTTPS que chegam às aplicações.

Pode ser associado a [[Amazon CloudFront]], Application Load Balancer, [[Amazon API Gateway]] e outros recursos compatíveis.

Em AWS WAF, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

AWS WAF é o firewall de aplicação web da AWS.

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

**O que Ele Analisa**

AWS WAF pode analisar:

* IP de origem;
* headers;
* query string;
* URI path;
* método HTTP;
* corpo da requisição;
* tamanho;
* padrões;
* labels;
* reputação;
* taxa de requisições.

**Web ACL**

A configuração principal é a [[Web ACLs|Web ACL]].

Ela contém regras e define a ação padrão para requisições.

**Regras**

[[Regras do AWS WAF]] podem ser customizadas ou gerenciadas.

[[Managed Rules do AWS WAF]] ajudam a bloquear padrões conhecidos, como ataques comuns contra aplicações web.

**Rate Limiting**

Com [[Rate Limiting]], o WAF pode limitar requisições por origem ou padrão, ajudando contra abuso e ataques volumétricos de camada 7.

**Onde Pode Ser Usado**

* CloudFront;
* Application Load Balancer;
* [[APIs|API]] Gateway;
* AppSync.

---

## Exemplo prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

Não confunda controles de segurança diferentes. [[AWS Identity and Access Management (IAM)|IAM]] decide permissões, KMS protege chaves, CloudTrail registra ações, GuardDuty detecta comportamento suspeito, WAF filtra tráfego de aplicação e Shield atua contra DDoS.

---

## Cuidados

**Limite**

WAF não substitui autenticação, autorização, correção de vulnerabilidades ou desenho seguro.

Ele é uma camada de proteção, não a segurança inteira.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

WAF não substitui segurança da aplicação. Ele filtra tráfego, mas código vulnerável continua precisando ser corrigido.

---

## Relação com outras notas

- [[Amazon CloudFront]]
- [[Amazon API Gateway]]
- [[Web ACLs]]
- [[Regras do AWS WAF]]
- [[Managed Rules do AWS WAF]]
- [[Rate Limiting]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
