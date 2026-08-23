Credenciais Temporárias são credenciais com tempo de expiração.

Na AWS, elas são frequentemente emitidas pelo [[AWS Security Token Service (STS)]] quando uma entidade assume uma [[Roles do IAM|role]].

Em Credenciais Temporárias, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Credenciais Temporárias deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

---

## Por que existe

Credenciais Temporárias existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Por que São Melhores**

Se uma credencial temporária vaza, ela deixa de funcionar após expirar.

Isso reduz janela de exploração.

**Uso em Serviços**

Serviços como [[Amazon EC2]] e [[AWS Lambda]] podem usar roles para obter credenciais temporárias sem armazenar chaves no código.

---

## Exemplo prático

Uma aplicação em [[Amazon EC2|EC2]] precisa ler [[Amazon S3|S3]].

Em vez de colocar access key no servidor, associa-se uma role à instância. A AWS fornece credenciais temporárias automaticamente.

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

Não confunda controles de segurança diferentes. [[AWS Identity and Access Management (IAM)|IAM]] decide permissões, KMS protege chaves, CloudTrail registra ações, GuardDuty detecta comportamento suspeito, WAF filtra tráfego de aplicação e Shield atua contra DDoS.

---

## Cuidados

**Limite**

Credenciais temporárias não corrigem permissões amplas.

Se a role permite demais, o risco continua alto durante a validade da credencial.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

## Relação com outras notas

- [[AWS Security Token Service (STS)]]
- [[Roles do IAM]]
- [[Amazon EC2]]
- [[AWS Lambda]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
