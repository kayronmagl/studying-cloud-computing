AWS Security Token Service, ou AWS STS, é o serviço que emite credenciais temporárias na AWS.

Ele é usado principalmente quando uma entidade assume uma [[Roles do IAM|role]].


Em AWS Security Token Service (STS), pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Credenciais Temporárias

Credenciais temporárias possuem tempo de expiração.

Elas reduzem risco porque não permanecem válidas indefinidamente como access keys de longo prazo.

---

## AssumeRole

Um caso comum é `AssumeRole`.

Uma entidade autorizada assume uma role e recebe credenciais temporárias para executar ações permitidas por essa role.

---

## Exemplos

* usuário assume role administrativa por tempo limitado;
* aplicação em EC2 usa role para acessar S3;
* Lambda usa role para gravar logs;
* conta externa assume role com permissão restrita.

---

## Relação com Segurança

STS é uma das bases para evitar credenciais permanentes em aplicações.

Em vez de colocar chaves no código, a aplicação usa role e recebe credenciais temporárias automaticamente.

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
