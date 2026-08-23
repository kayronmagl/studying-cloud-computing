AWS Shield Standard é a proteção DDoS automática incluída para clientes AWS.

Ele ajuda a proteger contra ataques comuns de camada de rede e transporte.

Em AWS Shield Standard, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

[[AWS Shield]] protege contra ataques DDoS.

Shield Standard é incluído automaticamente para clientes AWS. Shield Advanced oferece recursos adicionais, suporte e proteção mais robusta para workloads críticos.

---

## Por que existe

AWS Shield Standard existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Características**

* ativado automaticamente;
* sem custo adicional direto;
* protege contra padrões frequentes de DDoS;
* funciona melhor com serviços como [[Amazon CloudFront]] e [[Amazon Route 53]].

**DDoS**

Ataque DDoS tenta indisponibilizar serviço com tráfego excessivo ou malicioso.

---

## Exemplo prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

Não confunda controles de segurança diferentes. [[AWS Identity and Access Management (IAM)|IAM]] decide permissões, KMS protege chaves, CloudTrail registra ações, GuardDuty detecta comportamento suspeito, WAF filtra tráfego de aplicação e Shield atua contra DDoS.

---

## Cuidados

**Limite**

Shield Standard não oferece todos os recursos de visibilidade, suporte e resposta do [[AWS Shield Advanced]].

Para aplicações críticas expostas à internet, Shield Advanced pode ser avaliado.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Shield não impede todos os ataques de aplicação. Para camada HTTP, combine com WAF, CloudFront, rate limiting e boas práticas.

---

## Relação com outras notas

**Relação com WAF**

Shield Standard não substitui [[AWS WAF]].

WAF atua em regras de aplicação web. Shield atua na defesa contra DDoS.

**Relação com WAF na prática**

Shield atua contra DDoS. WAF atua no nível de requisições web e regras de aplicação.
