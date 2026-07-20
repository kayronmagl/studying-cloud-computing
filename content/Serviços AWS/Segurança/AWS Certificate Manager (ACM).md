AWS Certificate Manager, ou ACM, é o serviço da AWS para provisionar, gerenciar e renovar certificados TLS/SSL.

Ele é usado para habilitar HTTPS em serviços como [[Amazon CloudFront]], load balancers e APIs.

---

## Visão geral

Em AWS Certificate Manager (ACM), pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Criptografia em Trânsito

ACM está ligado à [[Criptografia em Trânsito]].

Ele permite que clientes se comuniquem com aplicações usando TLS, protegendo dados contra interceptação no caminho.

---

## Integração

ACM se integra com:

* [[Elastic Load Balancing]];
* [[Amazon CloudFront]];
* [[Amazon API Gateway]];
* outros serviços compatíveis.

---

## Renovação

Certificados gerenciados pelo ACM podem ser renovados automaticamente em muitos cenários, reduzindo risco de expiração.

---

## Cuidado

Ter HTTPS não garante aplicação segura.

TLS protege transporte, mas não corrige autorização ruim, vulnerabilidades ou vazamento de dados.

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
