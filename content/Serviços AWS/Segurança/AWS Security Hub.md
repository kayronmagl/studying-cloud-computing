AWS Security Hub é o serviço da AWS para centralizar achados de segurança e postura de conformidade.

Ele consolida informações de serviços como [[Amazon GuardDuty]], [[Amazon Inspector]], [[Amazon Macie]], [[AWS Config]] e integrações de parceiros.

Em AWS Security Hub, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

AWS Security Hub deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

AWS Security Hub existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Função**

Security Hub ajuda a responder:

* qual é a postura de segurança da conta?
* quais findings existem?
* quais são críticos?
* quais padrões de conformidade estão falhando?

**CSPM**

Security Hub funciona como uma camada de Cloud Security Posture Management em ambientes AWS.

Ele não substitui os serviços que geram os achados, mas centraliza visão.

**Uso**

É útil em ambientes com múltiplas contas, muitos recursos e necessidade de priorização.

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

Centralizar findings não é o mesmo que corrigir.

É preciso processo de resposta, responsáveis e automação quando fizer sentido.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

- [[Amazon GuardDuty]]
- [[Amazon Inspector]]
- [[Amazon Macie]]
- [[AWS Config]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
