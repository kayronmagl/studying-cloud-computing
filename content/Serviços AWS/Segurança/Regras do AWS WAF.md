Regras do AWS WAF definem critérios para inspecionar e tratar requisições web.

Elas são avaliadas dentro de uma [[Web ACLs|Web ACL]].

Em Regras do AWS WAF, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

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

**Tipos de Critério**

Regras podem avaliar:

* IP;
* país;
* header;
* cookie;
* query string;
* corpo;
* URI;
* método HTTP;
* tamanho;
* padrões regex;
* taxa de requisições.

**Ações**

Uma regra pode permitir, bloquear, contar ou desafiar requisições.

O modo `count` é útil para testar uma regra antes de bloquear tráfego real.

**Prioridade**

Regras possuem ordem de avaliação.

Isso importa porque regras específicas podem precisar vir antes de regras gerais.

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

Regras mal desenhadas podem causar falso positivo.

Segurança de aplicação precisa equilibrar proteção e disponibilidade.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

WAF não substitui segurança da aplicação. Ele filtra tráfego, mas código vulnerável continua precisando ser corrigido.

---

## Relação com outras notas

- [[Web ACLs]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
