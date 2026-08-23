AWS Secrets Manager é o serviço da AWS para armazenar, recuperar e rotacionar segredos.

Segredos incluem senhas de banco, tokens, chaves de [[APIs|API]], credenciais e informações sensíveis que não devem ficar no código.

Em AWS Secrets Manager, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

AWS Secrets Manager deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Aplicações frequentemente precisam de credenciais.

Guardar essas credenciais em código, arquivos locais ou variáveis sem controle aumenta risco de vazamento.

Secrets Manager centraliza armazenamento, acesso controlado e rotação.

---

## Como funciona

**Integração**

Pode ser usado por aplicações em [[Amazon EC2]], [[AWS Lambda]], containers e outros serviços.

O acesso deve ser concedido por [[Roles do IAM]] com menor privilégio.

**Rotação**

Secrets Manager pode ajudar a rotacionar certos tipos de segredo, como credenciais de banco.

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

Guardar segredo em Secrets Manager não resolve tudo.

A aplicação ainda precisa controlar quem pode ler o segredo e evitar registrá-lo em logs.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

**Relação com KMS**

Segredos podem ser criptografados usando [[AWS Key Management Service (KMS)]].
