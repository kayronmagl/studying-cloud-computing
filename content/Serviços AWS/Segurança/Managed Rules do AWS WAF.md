Managed Rules do AWS WAF são conjuntos de regras gerenciadas pela AWS ou por fornecedores parceiros.

Elas ajudam a proteger contra padrões conhecidos de ataque sem exigir que a equipe escreva todas as regras manualmente.

Em Managed Rules do AWS WAF, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

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

**Exemplos de Proteção**

Managed rules podem ajudar contra:

* padrões comuns de exploração;
* SQL injection;
* cross-site scripting;
* bots;
* IPs de reputação ruim;
* requisições anômalas.

**Vantagem**

Reduzem esforço inicial e trazem conhecimento operacional embutido.

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

Managed rules ainda precisam ser testadas.

Uma regra pode bloquear tráfego legítimo dependendo da aplicação.

O ideal é observar em modo count antes de aplicar bloqueio amplo em produção.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

WAF não substitui segurança da aplicação. Ele filtra tráfego, mas código vulnerável continua precisando ser corrigido.

---

## Relação com outras notas

**Relação com WAF**

Managed rules vivem dentro de [[Web ACLs]] do [[AWS WAF]].
