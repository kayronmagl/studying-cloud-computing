Access Keys são [[Credenciais de Longo Prazo|credenciais de longo prazo]] usadas para acesso programático à AWS por [[AWS CLI]], [[AWS SDKs]] e [[APIs]].

Elas normalmente possuem duas partes: access key ID e secret access key.

Em Access Keys, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Access Keys deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

---

## Por que existe

Access Keys existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Risco**

Access keys são perigosas quando ficam permanentes e espalhadas.

Vazamentos em repositórios, logs ou máquinas locais podem permitir acesso à conta.

---

## Exemplo prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

**Quando Usar**

Podem ser necessárias em integrações externas, automações fora da AWS ou laboratórios.

Mesmo nesses casos, devem ter escopo limitado.

---

## Cuidados

**Boas Práticas**

* evitar access keys para aplicações na AWS;
* preferir [[Roles do IAM]];
* usar rotação;
* remover chaves sem uso;
* aplicar menor privilégio;
* não armazenar em código;
* monitorar uso com [[AWS CloudTrail]].

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

## Relação com outras notas

- [[Credenciais de Longo Prazo]]
- [[AWS CLI]]
- [[AWS SDKs]]
- [[APIs]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
- [[Roles do IAM]]
