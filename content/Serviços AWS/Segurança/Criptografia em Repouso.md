Criptografia em Repouso protege dados armazenados.

Ela se aplica quando dados estão em disco, bucket, snapshot, banco, backup ou outro meio persistente.

---

## Visão geral

Em Criptografia em Repouso, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Onde Aparece

Na AWS, criptografia em repouso aparece em:

* [[Amazon S3]];
* [[Amazon EBS]];
* [[Amazon RDS]];
* [[Amazon DynamoDB]];
* [[AWS Secrets Manager]];
* [[AWS CloudTrail]] logs;
* backups e snapshots.

---

## Relação com KMS

Muitos serviços usam [[AWS Key Management Service (KMS)]] para gerenciar chaves de criptografia.

---

## Limite

Criptografia em repouso não impede acesso autorizado indevido.

Se uma identidade possui permissão para ler e descriptografar, ela acessa o dado.

---

## Uso Correto

Combine criptografia com IAM, políticas, logs, separação de funções e revisão de acesso.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

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
