Políticas Baseadas em Identidade são políticas anexadas a identidades [[AWS Identity and Access Management (IAM)|IAM]].

Elas podem ser anexadas a [[Usuários do IAM]], [[Grupos de Usuários do IAM]] ou [[Roles do IAM]].

Em Políticas Baseadas em Identidade, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Políticas Baseadas em Identidade deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

---

## Por que existe

Políticas Baseadas em Identidade existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Função**

Elas respondem:

* esta identidade pode fazer quais ações?

Exemplo: uma role de aplicação pode ter permissão para ler objetos de um [[Buckets S3|bucket]] específico e escrever logs no CloudWatch.

**Onde Usar**

São usadas para conceder permissões a pessoas, aplicações, serviços e automações.

---

## Exemplo prático

Uma role [[AWS Lambda|Lambda]] possui política permitindo:

* s3: GetObject
* logs: CreateLogStream
* logs: PutLogEvents

Isso permite que a função leia objetos e publique logs, sem conceder acesso amplo à conta.

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

**Comparação**

[[Políticas Baseadas em Recurso]] são anexadas ao recurso.

Políticas baseadas em identidade são anexadas à identidade.

Em muitos cenários, as duas podem interagir.

---

## Cuidados

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

## Relação com outras notas

- [[Usuários do IAM]]
- [[Grupos de Usuários do IAM]]
- [[Roles do IAM]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
- [[Políticas Baseadas em Recurso]]
