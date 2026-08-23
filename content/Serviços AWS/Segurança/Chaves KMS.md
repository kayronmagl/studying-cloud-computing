Chaves KMS são chaves criptográficas gerenciadas pelo [[AWS Key Management Service (KMS)]].

Elas controlam operações como criptografar, descriptografar, gerar data keys e assinar/verificar, dependendo do tipo de chave.

Em Chaves KMS, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Chaves KMS deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Chaves KMS existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Políticas de Chave**

Chaves KMS possuem políticas próprias.

Essas políticas definem quem pode administrar ou usar a chave.

**Uso**

Chaves KMS aparecem em:

* criptografia de [[Buckets S3|buckets S3]];
* volumes EBS;
* bancos [[Amazon RDS|RDS]];
* segredos;
* logs;
* trilhas CloudTrail.

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

Perder controle de uma chave pode tornar dados inacessíveis.

Permissões amplas em chaves também podem expor dados sensíveis.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

**Relação com [[AWS Identity and Access Management (IAM)|IAM]]**

Permissões [[AWS Identity and Access Management (IAM)|IAM]] e políticas de chave podem atuar juntas.

Uma identidade pode precisar de permissão [[AWS Identity and Access Management (IAM)|IAM]] e permissão na key policy.

- [[AWS Key Management Service (KMS)]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS CloudTrail]]
