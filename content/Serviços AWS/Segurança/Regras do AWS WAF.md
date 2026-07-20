Regras do AWS WAF definem critérios para inspecionar e tratar requisições web.

Elas são avaliadas dentro de uma [[Web ACLs|Web ACL]].

---

## Visão geral

Em Regras do AWS WAF, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Tipos de Critério

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

---

## Ações

Uma regra pode permitir, bloquear, contar ou desafiar requisições.

O modo `count` é útil para testar uma regra antes de bloquear tráfego real.

---

## Prioridade

Regras possuem ordem de avaliação.

Isso importa porque regras específicas podem precisar vir antes de regras gerais.

---

## Cuidado

Regras mal desenhadas podem causar falso positivo.

Segurança de aplicação precisa equilibrar proteção e disponibilidade.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

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
