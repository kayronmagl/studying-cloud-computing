AWS Config é o serviço da AWS que registra configurações de recursos e avalia conformidade ao longo do tempo.

Enquanto [[AWS CloudTrail]] registra ações, Config acompanha estado e mudanças de configuração.

---

## Visão geral

Em AWS Config, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Perguntas que Responde

* este bucket ficou público?
* quando o security group mudou?
* qual era a configuração antes?
* este recurso está em conformidade?


---

## Rules

Config Rules avaliam recursos contra regras.

Exemplo:

* verificar se buckets S3 bloqueiam acesso público;
* verificar se CloudTrail está habilitado;
* verificar se volumes estão criptografados;
* verificar se security groups não expõem portas sensíveis.

---

## Relação com Governança

AWS Config ajuda a detectar drift e violações de política.

É útil em ambientes que precisam de auditoria e conformidade.

---

## Cuidado

Config detecta e avalia.

Correção pode exigir automação, processo ou intervenção.

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
