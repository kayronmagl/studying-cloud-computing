Amazon Macie é o serviço da AWS para descoberta e proteção de dados sensíveis, especialmente em [[Amazon S3]].

Ele ajuda a identificar dados como informações pessoais, credenciais e dados sensíveis armazenados em buckets.

---

## Visão geral

Em Amazon Macie, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Papel

Macie responde perguntas como:


* existem dados sensíveis neste bucket?
* há dados pessoais expostos?
* quais buckets merecem atenção?


---

## Relação com S3

Macie é muito útil em ambientes com muitos buckets e grande volume de objetos.

Ele ajuda a descobrir riscos que não aparecem apenas olhando permissões.

---

## Exemplo

Uma organização pode descobrir que arquivos com dados pessoais foram enviados para um bucket sem classificação adequada.

---

## Cuidado

Macie ajuda a descobrir.

A correção envolve políticas, criptografia, acesso, retenção e governança.

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
