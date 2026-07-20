AWS Shield é o serviço da AWS para proteção contra ataques DDoS.

Ele possui dois níveis principais: [[AWS Shield Standard]] e [[AWS Shield Advanced]].

---

## Visão geral

Em AWS Shield, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Shield Standard

Todos os clientes AWS recebem proteção básica automática contra ataques DDoS comuns de camada de rede e transporte.

Ele é especialmente útil com recursos como [[Amazon CloudFront]], [[Amazon Route 53]] e outros serviços expostos.

---

## Shield Advanced

Shield Advanced adiciona recursos para aplicações críticas:

* proteção avançada;
* visibilidade adicional;
* suporte especializado;
* integração com WAF;
* recursos de resposta DDoS;
* proteção de custo em certos cenários.

---

## Relação com WAF

[[AWS WAF]] protege aplicações web por regras HTTP/HTTPS.

Shield protege contra DDoS em diferentes camadas.

Eles são complementares.

---

## Relação com Arquitetura

Shield funciona melhor quando a aplicação já usa borda e serviços resilientes, como CloudFront, Route 53, load balancers e escalabilidade.

---

## Cuidado

Shield não corrige aplicação vulnerável.

Ataques de camada 7 podem exigir WAF, rate limiting e desenho adequado de backend.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

## Explicação principal

AWS Shield protege contra ataques DDoS.

Shield Standard é incluído automaticamente para clientes AWS. Shield Advanced oferece recursos adicionais, suporte e proteção mais robusta para workloads críticos.

## DDoS

Ataque DDoS tenta indisponibilizar serviço com tráfego excessivo ou malicioso.

## Relação com WAF na prática

Shield atua contra DDoS. WAF atua no nível de requisições web e regras de aplicação.

## Cuidado importante

Shield não impede todos os ataques de aplicação. Para camada HTTP, combine com WAF, CloudFront, rate limiting e boas práticas.
