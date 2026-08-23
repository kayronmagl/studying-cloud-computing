Web ACLs são listas de controle de acesso web usadas pelo [[AWS WAF]].

Uma Web ACL contém regras que determinam como tratar requisições HTTP e HTTPS.

Em Web ACLs, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Web ACLs deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Web ACLs existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Estrutura**

Uma Web ACL possui:

* ação padrão;
* regras;
* prioridades;
* condições;
* métricas;
* integração com recursos protegidos.

**Ações**

Regras podem:

* permitir;
* bloquear;
* contar;
* desafiar;
* aplicar CAPTCHA, dependendo do recurso e configuração.

**Associação**

Uma Web ACL pode ser associada a recursos como [[Amazon CloudFront]], Application Load Balancer e [[Amazon API Gateway]].

**Observabilidade**

WAF deve ser monitorado.

Regras agressivas podem bloquear usuários legítimos. Regras fracas podem deixar ataque passar.

---

## Exemplo prático

Uma Web ACL pode bloquear IPs maliciosos, limitar taxa de requisições e aplicar managed rules contra padrões comuns de exploração.

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

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

- [[AWS WAF]]
- [[Amazon CloudFront]]
- [[Amazon API Gateway]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
