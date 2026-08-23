Criptografia em Repouso protege dados armazenados.

Ela se aplica quando dados estão em disco, [[Buckets S3|bucket]], snapshot, banco, backup ou outro meio persistente.

Em Criptografia em Repouso, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Criptografia em Repouso deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Criptografia em Repouso existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Onde Aparece**

Na AWS, criptografia em repouso aparece em:

* [[Amazon S3]];
* [[Amazon EBS]];
* [[Amazon RDS]];
* [[Amazon DynamoDB]];
* [[AWS Secrets Manager]];
* [[AWS CloudTrail]] logs;
* backups e snapshots.

**Uso Correto**

Combine criptografia com [[AWS Identity and Access Management (IAM)|IAM]], políticas, logs, separação de funções e revisão de acesso.

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

**Limite**

Criptografia em repouso não impede acesso autorizado indevido.

Se uma identidade possui permissão para ler e descriptografar, ela acessa o dado.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

**Relação com KMS**

Muitos serviços usam [[AWS Key Management Service (KMS)]] para gerenciar chaves de criptografia.
