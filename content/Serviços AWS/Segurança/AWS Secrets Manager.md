AWS Secrets Manager é o serviço da AWS para armazenar, recuperar e rotacionar segredos.

Segredos incluem senhas de banco, tokens, chaves de API, credenciais e informações sensíveis que não devem ficar no código.


Em AWS Secrets Manager, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Problema que Resolve

Aplicações frequentemente precisam de credenciais.

Guardar essas credenciais em código, arquivos locais ou variáveis sem controle aumenta risco de vazamento.

Secrets Manager centraliza armazenamento, acesso controlado e rotação.

---

## Integração

Pode ser usado por aplicações em [[Amazon EC2]], [[AWS Lambda]], containers e outros serviços.

O acesso deve ser concedido por [[Roles do IAM]] com menor privilégio.

---

## Rotação

Secrets Manager pode ajudar a rotacionar certos tipos de segredo, como credenciais de banco.

---

## Relação com KMS

Segredos podem ser criptografados usando [[AWS Key Management Service (KMS)]].

---

## Cuidado

Guardar segredo em Secrets Manager não resolve tudo.

A aplicação ainda precisa controlar quem pode ler o segredo e evitar registrá-lo em logs.

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
