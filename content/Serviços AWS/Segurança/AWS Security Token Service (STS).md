AWS Security Token Service, ou AWS STS, é o serviço que emite credenciais temporárias na AWS.

Ele é usado principalmente quando uma entidade assume uma [[Roles do IAM|role]].

Em AWS Security Token Service (STS), pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

AWS Security Token Service (STS) deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

AWS Security Token Service (STS) existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Credenciais Temporárias**

Credenciais temporárias possuem tempo de expiração.

Elas reduzem risco porque não permanecem válidas indefinidamente como access keys de longo prazo.

**AssumeRole**

Um caso comum é `AssumeRole`.

Uma entidade autorizada assume uma role e recebe credenciais temporárias para executar ações permitidas por essa role.

---

## Exemplo prático

* usuário assume role administrativa por tempo limitado;
* aplicação em [[Amazon EC2|EC2]] usa role para acessar [[Amazon S3|S3]];
* [[AWS Lambda|Lambda]] usa role para gravar logs;
* conta externa assume role com permissão restrita.

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

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

**Relação com Segurança**

STS é uma das bases para evitar credenciais permanentes em aplicações.

Em vez de colocar chaves no código, a aplicação usa role e recebe credenciais temporárias automaticamente.

- [[Roles do IAM]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
