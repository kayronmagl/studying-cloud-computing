Segurança na AWS é o conjunto de práticas, serviços e decisões arquiteturais usados para proteger contas, identidades, redes, aplicações, dados e operações dentro da nuvem da Amazon.

Segurança em nuvem não deve ser entendida como um produto isolado. Ela é uma propriedade do sistema inteiro. Uma aplicação pode usar [[Amazon EC2]], [[Amazon S3]], [[Amazon RDS]], [[AWS Lambda]], [[Amazon VPC]] e [[Amazon CloudFront]], mas todos esses recursos precisam de identidade, permissão, criptografia, rede segura, logs, auditoria e detecção de ameaças.


Em Segurança na AWS, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Eixos da Segurança

Os principais eixos são:

* [[Modelo de Responsabilidade Compartilhada]];
* [[AWS Identity and Access Management (IAM)]];
* segurança de rede;
* [[Segurança de Aplicações na AWS]];
* proteção contra [[Ataques DoS e DDoS]];
* criptografia;
* proteção de segredos;
* auditoria;
* detecção de ameaças;
* conformidade.

Nenhum desses eixos substitui os outros.

---

## Segurança por Camadas

Segurança por camadas significa combinar controles complementares.

Exemplo:


* CloudFront: ↓.
* [[AWS WAF]]: ↓.
* Load Balancer: ↓.
* [[Security Groups]]: ↓.
* Aplicação: ↓.
* [[AWS Identity and Access Management (IAM)|IAM]]: ↓.
* [[AWS Key Management Service (KMS)|KMS]]: ↓.
* CloudTrail / GuardDuty


Se uma camada falha, outras reduzem impacto.

---

## Erro Comum

O erro mais comum é pensar que “estar na AWS” já torna o sistema seguro.

A AWS fornece infraestrutura e ferramentas robustas, mas o cliente ainda configura permissões, redes, aplicações, dados e políticas.

Por isso, segurança na AWS começa no desenho, não apenas depois do deploy.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

## Como entender isso

Este conceito pertence ao módulo de segurança na AWS.

## Ponto central

Segurança combina IAM, rede, criptografia, auditoria, detecção e proteção de aplicação.

## Como Diferenciar

* IAM controla permissões.
* KMS gerencia chaves.
* WAF filtra HTTP/HTTPS.
* Shield protege contra DDoS.
* CloudTrail audita chamadas de API.
* GuardDuty detecta ameaças.

## Cuidado importante

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Conceitos que completam o assunto

O nome curto [[AWS KMS]] se refere ao [[AWS Key Management Service (KMS)]], usado para controlar chaves criptográficas e integrar criptografia a vários serviços AWS.
