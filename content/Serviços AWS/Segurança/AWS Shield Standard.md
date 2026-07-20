AWS Shield Standard é a proteção DDoS automática incluída para clientes AWS.

Ele ajuda a proteger contra ataques comuns de camada de rede e transporte.

---

## Visão geral

Em AWS Shield Standard, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Características

* ativado automaticamente;
* sem custo adicional direto;
* protege contra padrões frequentes de DDoS;
* funciona melhor com serviços como [[Amazon CloudFront]] e [[Amazon Route 53]].

---

## Limite

Shield Standard não oferece todos os recursos de visibilidade, suporte e resposta do [[AWS Shield Advanced]].

Para aplicações críticas expostas à internet, Shield Advanced pode ser avaliado.

---

## Relação com WAF

Shield Standard não substitui [[AWS WAF]].

WAF atua em regras de aplicação web. Shield atua na defesa contra DDoS.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

## Explicação principal

[[AWS Shield]] protege contra ataques DDoS.

Shield Standard é incluído automaticamente para clientes AWS. Shield Advanced oferece recursos adicionais, suporte e proteção mais robusta para workloads críticos.

## DDoS

Ataque DDoS tenta indisponibilizar serviço com tráfego excessivo ou malicioso.

## Relação com WAF na prática

Shield atua contra DDoS. WAF atua no nível de requisições web e regras de aplicação.

## Cuidado importante

Shield não impede todos os ataques de aplicação. Para camada HTTP, combine com WAF, CloudFront, rate limiting e boas práticas.
