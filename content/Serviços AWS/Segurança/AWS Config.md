AWS Config é o serviço da AWS que registra configurações de recursos e avalia conformidade ao longo do tempo.

Enquanto [[AWS CloudTrail]] registra ações, Config acompanha estado e mudanças de configuração.

Em AWS Config, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

AWS Config deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

AWS Config existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Perguntas que Responde**

* este [[Buckets S3|bucket]] ficou público?
* quando o security group mudou?
* qual era a configuração antes?
* este recurso está em conformidade?

**Rules**

Config Rules avaliam recursos contra regras.

Exemplo:

* verificar se [[Buckets S3|buckets S3]] bloqueiam acesso público;
* verificar se CloudTrail está habilitado;
* verificar se volumes estão criptografados;
* verificar se security groups não expõem portas sensíveis.

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

Config detecta e avalia.

Correção pode exigir automação, processo ou intervenção.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

**Relação com Governança**

AWS Config ajuda a detectar drift e violações de política.

É útil em ambientes que precisam de auditoria e conformidade.

- [[AWS CloudTrail]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
