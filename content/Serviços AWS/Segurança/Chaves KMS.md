Chaves KMS são chaves criptográficas gerenciadas pelo [[AWS Key Management Service (KMS)]].

Elas controlam operações como criptografar, descriptografar, gerar data keys e assinar/verificar, dependendo do tipo de chave.

---

## Visão geral

Em Chaves KMS, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Políticas de Chave

Chaves KMS possuem políticas próprias.

Essas políticas definem quem pode administrar ou usar a chave.

---

## Relação com IAM

Permissões IAM e políticas de chave podem atuar juntas.

Uma identidade pode precisar de permissão IAM e permissão na key policy.

---

## Uso

Chaves KMS aparecem em:

* criptografia de buckets S3;
* volumes EBS;
* bancos RDS;
* segredos;
* logs;
* trilhas CloudTrail.

---

## Cuidado

Perder controle de uma chave pode tornar dados inacessíveis.

Permissões amplas em chaves também podem expor dados sensíveis.

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
