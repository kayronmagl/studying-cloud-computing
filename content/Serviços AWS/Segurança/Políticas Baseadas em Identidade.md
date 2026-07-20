Políticas Baseadas em Identidade são políticas anexadas a identidades IAM.

Elas podem ser anexadas a [[Usuários do IAM]], [[Grupos de Usuários do IAM]] ou [[Roles do IAM]].

---

## Visão geral

Em Políticas Baseadas em Identidade, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Função

Elas respondem:


* esta identidade pode fazer quais ações?


Exemplo: uma role de aplicação pode ter permissão para ler objetos de um bucket específico e escrever logs no CloudWatch.

---

## Onde Usar

São usadas para conceder permissões a pessoas, aplicações, serviços e automações.

---

## Comparação

[[Políticas Baseadas em Recurso]] são anexadas ao recurso.

Políticas baseadas em identidade são anexadas à identidade.

Em muitos cenários, as duas podem interagir.

---

## Exemplo

Uma role Lambda possui política permitindo:


* s3: GetObject
* logs: CreateLogStream
* logs: PutLogEvents


Isso permite que a função leia objetos e publique logs, sem conceder acesso amplo à conta.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.
