Web ACLs são listas de controle de acesso web usadas pelo [[AWS WAF]].

Uma Web ACL contém regras que determinam como tratar requisições HTTP e HTTPS.

---

## Visão geral

Em Web ACLs, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Estrutura

Uma Web ACL possui:

* ação padrão;
* regras;
* prioridades;
* condições;
* métricas;
* integração com recursos protegidos.

---

## Ações

Regras podem:

* permitir;
* bloquear;
* contar;
* desafiar;
* aplicar CAPTCHA, dependendo do recurso e configuração.

---

## Associação

Uma Web ACL pode ser associada a recursos como [[Amazon CloudFront]], Application Load Balancer e [[Amazon API Gateway]].

---

## Exemplo

Uma Web ACL pode bloquear IPs maliciosos, limitar taxa de requisições e aplicar managed rules contra padrões comuns de exploração.

---

## Observabilidade

WAF deve ser monitorado.

Regras agressivas podem bloquear usuários legítimos. Regras fracas podem deixar ataque passar.

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
