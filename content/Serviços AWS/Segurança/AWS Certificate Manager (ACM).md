AWS Certificate Manager, ou ACM, é o serviço da AWS para provisionar, gerenciar e renovar certificados TLS/SSL.

Ele é usado para habilitar HTTPS em serviços como [[Amazon CloudFront]], load balancers e [[APIs|APIs]].

Em AWS Certificate Manager (ACM), pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

AWS Certificate Manager (ACM) deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

AWS Certificate Manager (ACM) existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Criptografia em Trânsito**

ACM está ligado à [[Criptografia em Trânsito]].

Ele permite que clientes se comuniquem com aplicações usando TLS, protegendo dados contra interceptação no caminho.

**Integração**

ACM se integra com:

* [[Elastic Load Balancing]];
* [[Amazon CloudFront]];
* [[Amazon API Gateway]];
* outros serviços compatíveis.

**Renovação**

Certificados gerenciados pelo ACM podem ser renovados automaticamente em muitos cenários, reduzindo risco de expiração.

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

Ter HTTPS não garante aplicação segura.

TLS protege transporte, mas não corrige autorização ruim, vulnerabilidades ou vazamento de dados.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

- [[Amazon CloudFront]]
- [[Criptografia em Trânsito]]
- [[Elastic Load Balancing]]
- [[Amazon API Gateway]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
