Amazon Macie é o serviço da AWS para descoberta e proteção de dados sensíveis, especialmente em [[Amazon S3]].

Ele ajuda a identificar dados como informações pessoais, credenciais e dados sensíveis armazenados em [[Buckets S3|buckets]].

Em Amazon Macie, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Amazon Macie deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Amazon Macie existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Papel**

Macie responde perguntas como:

* existem dados sensíveis neste [[Buckets S3|bucket]]?
* há dados pessoais expostos?
* quais [[Buckets S3|buckets]] merecem atenção?

---

## Exemplo prático

Uma organização pode descobrir que arquivos com dados pessoais foram enviados para um [[Buckets S3|bucket]] sem classificação adequada.

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

Macie ajuda a descobrir.

A correção envolve políticas, criptografia, acesso, retenção e governança.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

**Relação com [[Amazon S3|S3]]**

Macie é muito útil em ambientes com muitos [[Buckets S3|buckets]] e grande volume de objetos.

Ele ajuda a descobrir riscos que não aparecem apenas olhando permissões.

- [[Amazon S3]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
