AWS Security Hub é o serviço da AWS para centralizar achados de segurança e postura de conformidade.

Ele consolida informações de serviços como [[Amazon GuardDuty]], [[Amazon Inspector]], [[Amazon Macie]], [[AWS Config]] e integrações de parceiros.

---

## Visão geral

Em AWS Security Hub, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Função

Security Hub ajuda a responder:


* qual é a postura de segurança da conta?
* quais findings existem?
* quais são críticos?
* quais padrões de conformidade estão falhando?


---

## CSPM

Security Hub funciona como uma camada de Cloud Security Posture Management em ambientes AWS.

Ele não substitui os serviços que geram os achados, mas centraliza visão.

---

## Uso

É útil em ambientes com múltiplas contas, muitos recursos e necessidade de priorização.

---

## Cuidado

Centralizar findings não é o mesmo que corrigir.

É preciso processo de resposta, responsáveis e automação quando fizer sentido.

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
