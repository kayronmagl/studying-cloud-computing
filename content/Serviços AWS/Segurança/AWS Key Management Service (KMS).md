AWS Key Management Service, ou KMS, é o serviço da AWS para criar, gerenciar e usar chaves criptográficas.

Ele é usado por diversos serviços AWS para criptografia em repouso e controle de acesso a chaves.

Em AWS Key Management Service (KMS), pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

AWS Key Management Service (KMS) deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

AWS Key Management Service (KMS) existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Papel**

KMS não é apenas “guardar chave”.

Ele controla uso criptográfico por política, [[AWS Identity and Access Management (IAM)|IAM]], auditoria e integração com serviços.

**Chaves**

[[Chaves KMS]] podem ser gerenciadas pela AWS ou pelo cliente, dependendo do tipo.

Elas são usadas para criptografar dados em serviços como [[Amazon S3]], [[Amazon EBS]], [[Amazon RDS]], [[AWS CloudTrail]] e outros.

**Permissão**

Ter acesso ao dado não basta se a criptografia exige permissão de descriptografia na chave KMS.

Isso cria uma camada adicional de controle.

**Auditoria**

Uso de chaves pode ser auditado com [[AWS CloudTrail]].

**Nome curto do serviço**

[[AWS KMS]] é a forma abreviada de falar sobre o [[AWS Key Management Service (KMS)]], usado para criar e gerenciar chaves criptográficas.

---

## Exemplo prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

**Como Diferenciar**

* [[AWS Identity and Access Management (IAM)|IAM]] controla permissões.
* KMS gerencia chaves.
* WAF filtra HTTP/HTTPS.
* Shield protege contra DDoS.
* CloudTrail audita chamadas de [[APIs|API]].
* GuardDuty detecta ameaças.

---

## Cuidados

Criptografia não substitui permissão correta.

Se uma identidade tem permissão para ler o dado e descriptografar a chave, ela pode acessar o conteúdo.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

- [[Chaves KMS]]
- [[Amazon S3]]
- [[Amazon EBS]]
- [[Amazon RDS]]
- [[AWS CloudTrail]]
- [[AWS KMS]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
