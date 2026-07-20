AWS Firewall Manager é o serviço da AWS para gerenciar políticas de segurança em múltiplas contas e recursos.

Ele é especialmente útil em organizações com várias contas usando [[AWS Organizations]].

---

## Visão geral

Em AWS Firewall Manager, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## O que Gerencia

Firewall Manager pode ajudar a aplicar políticas relacionadas a:

* [[AWS WAF]];
* [[AWS Shield Advanced]];
* security groups;
* firewalls de rede;
* políticas centralizadas.

---

## Por que Importa

Em ambientes com muitas contas, configurar WAF e regras manualmente em cada aplicação é difícil.

Firewall Manager centraliza a aplicação de políticas e reduz inconsistência.

---

## Exemplo

Uma organização pode exigir que todos os CloudFront distributions usem uma Web ACL padrão com managed rules.

---

## Cuidado

Política centralizada precisa considerar exceções legítimas.

Segurança central não deve quebrar aplicações sem processo de governança.

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
