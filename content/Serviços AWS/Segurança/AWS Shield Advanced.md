AWS Shield Advanced é o nível avançado do [[AWS Shield]].

Ele oferece proteção adicional contra DDoS, visibilidade, suporte especializado e recursos voltados para aplicações críticas.

Em AWS Shield Advanced, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

[[AWS Shield]] protege contra ataques DDoS.

Shield Standard é incluído automaticamente para clientes AWS. Shield Advanced oferece recursos adicionais, suporte e proteção mais robusta para workloads críticos.

---

## Por que existe

AWS Shield Advanced existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**DDoS**

Ataque DDoS tenta indisponibilizar serviço com tráfego excessivo ou malicioso.

---

## Exemplo prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

**Quando Considerar**

Considere Shield Advanced quando:

* a aplicação é crítica;
* indisponibilidade gera alto impacto;
* há exposição pública significativa;
* a organização precisa de suporte DDoS especializado;
* há necessidade de visibilidade detalhada;
* há uso intenso de CloudFront, Route 53, Global Accelerator, load balancers ou Elastic IP.

---

## Cuidados

Contratar Shield Advanced não substitui arquitetura resiliente.

A aplicação ainda precisa de escalabilidade, borda, monitoramento e resposta a incidentes.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Shield não impede todos os ataques de aplicação. Para camada HTTP, combine com WAF, CloudFront, rate limiting e boas práticas.

---

## Relação com outras notas

**Relação com WAF**

Shield Advanced pode ser usado em conjunto com [[AWS WAF]].

WAF filtra tráfego HTTP/HTTPS. Shield Advanced ajuda na defesa DDoS e resposta operacional.

**Relação com WAF na prática**

Shield atua contra DDoS. WAF atua no nível de requisições web e regras de aplicação.
