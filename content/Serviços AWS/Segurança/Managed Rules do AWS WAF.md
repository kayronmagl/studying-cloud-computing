Managed Rules do AWS WAF são conjuntos de regras gerenciadas pela AWS ou por fornecedores parceiros.

Elas ajudam a proteger contra padrões conhecidos de ataque sem exigir que a equipe escreva todas as regras manualmente.


Em Managed Rules do AWS WAF, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Exemplos de Proteção

Managed rules podem ajudar contra:

* padrões comuns de exploração;
* SQL injection;
* cross-site scripting;
* bots;
* IPs de reputação ruim;
* requisições anômalas.

---

## Vantagem

Reduzem esforço inicial e trazem conhecimento operacional embutido.

---

## Cuidado

Managed rules ainda precisam ser testadas.

Uma regra pode bloquear tráfego legítimo dependendo da aplicação.

O ideal é observar em modo count antes de aplicar bloqueio amplo em produção.

---

## Relação com WAF

Managed rules vivem dentro de [[Web ACLs]] do [[AWS WAF]].

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
