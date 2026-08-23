AWS Firewall Manager é o serviço da AWS para gerenciar políticas de segurança em múltiplas contas e recursos.

Ele é especialmente útil em organizações com várias contas usando [[AWS Organizations]].

Em AWS Firewall Manager, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

AWS Firewall Manager deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Em ambientes com muitas contas, configurar WAF e regras manualmente em cada aplicação é difícil.

Firewall Manager centraliza a aplicação de políticas e reduz inconsistência.

---

## Como funciona

**O que Gerencia**

Firewall Manager pode ajudar a aplicar políticas relacionadas a:

* [[AWS WAF]];
* [[AWS Shield Advanced]];
* security groups;
* firewalls de rede;
* políticas centralizadas.

---

## Exemplo prático

Uma organização pode exigir que todos os CloudFront distributions usem uma Web ACL padrão com managed rules.

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

Política centralizada precisa considerar exceções legítimas.

Segurança central não deve quebrar aplicações sem processo de governança.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

- [[AWS Organizations]]
- [[AWS WAF]]
- [[AWS Shield Advanced]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
