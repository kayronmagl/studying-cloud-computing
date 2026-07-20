Access Keys são [[Credenciais de Longo Prazo|credenciais de longo prazo]] usadas para acesso programático à AWS por [[AWS CLI]], [[AWS SDKs]] e [[APIs]].

Elas normalmente possuem duas partes: access key ID e secret access key.

---

## Visão geral

Em Access Keys, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Risco

Access keys são perigosas quando ficam permanentes e espalhadas.

Vazamentos em repositórios, logs ou máquinas locais podem permitir acesso à conta.

---

## Boas Práticas

* evitar access keys para aplicações na AWS;
* preferir [[Roles do IAM]];
* usar rotação;
* remover chaves sem uso;
* aplicar menor privilégio;
* não armazenar em código;
* monitorar uso com [[AWS CloudTrail]].

---

## Quando Usar

Podem ser necessárias em integrações externas, automações fora da AWS ou laboratórios.

Mesmo nesses casos, devem ter escopo limitado.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.
