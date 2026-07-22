AWS Key Management Service, ou KMS, é o serviço da AWS para criar, gerenciar e usar chaves criptográficas.

Ele é usado por diversos serviços AWS para criptografia em repouso e controle de acesso a chaves.


Em AWS Key Management Service (KMS), pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Papel

KMS não é apenas “guardar chave”.

Ele controla uso criptográfico por política, IAM, auditoria e integração com serviços.

---

## Chaves

[[Chaves KMS]] podem ser gerenciadas pela AWS ou pelo cliente, dependendo do tipo.

Elas são usadas para criptografar dados em serviços como [[Amazon S3]], [[Amazon EBS]], [[Amazon RDS]], [[AWS CloudTrail]] e outros.

---

## Permissão

Ter acesso ao dado não basta se a criptografia exige permissão de descriptografia na chave KMS.

Isso cria uma camada adicional de controle.

---

## Auditoria

Uso de chaves pode ser auditado com [[AWS CloudTrail]].

---

## Cuidado

Criptografia não substitui permissão correta.

Se uma identidade tem permissão para ler o dado e descriptografar a chave, ela pode acessar o conteúdo.

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

---

## Nome curto do serviço

[[AWS KMS]] é a forma abreviada de falar sobre o [[AWS Key Management Service (KMS)]], usado para criar e gerenciar chaves criptográficas.
