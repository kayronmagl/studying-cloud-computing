Segurança de Aplicações na AWS é o conjunto de práticas e serviços usados para proteger aplicações contra abuso, exploração, tráfego malicioso, falhas de configuração e vulnerabilidades.

Ela envolve mais do que firewall. Inclui validação de entrada, autenticação, autorização, criptografia, logs, proteção de borda, varredura de vulnerabilidades e resposta a incidentes.

---

## Visão geral

Em Segurança de Aplicações na AWS, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Camadas

Uma aplicação web pode usar:

* [[Amazon CloudFront]];
* [[AWS WAF]];
* [[AWS Shield]];
* [[Elastic Load Balancing]];
* [[Amazon API Gateway]];
* [[AWS Certificate Manager (ACM)]];
* [[Amazon Inspector]];
* [[Amazon CloudWatch]];
* [[AWS CloudTrail]].

---

## WAF não Corrige Código Ruim

[[AWS WAF]] ajuda a bloquear padrões de ataque, mas a aplicação ainda precisa validar entradas, usar autenticação correta, proteger sessões, evitar SQL injection, proteger secrets e aplicar controle de autorização.

---

## Borda

CloudFront, WAF e Shield ajudam a filtrar e absorver tráfego antes que ele chegue ao backend.

Isso reduz carga, melhora latência e aumenta resiliência.

---

## Observabilidade

Sem logs e métricas, a equipe não sabe se a aplicação está sendo atacada.

Segurança de aplicação precisa de visibilidade contínua.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

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
