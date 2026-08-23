Políticas Baseadas em Recurso são políticas anexadas diretamente a um recurso AWS.

Elas definem quem pode acessar aquele recurso e em quais condições.

Em Políticas Baseadas em Recurso, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Políticas Baseadas em Recurso deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

---

## Por que existe

Políticas Baseadas em Recurso existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Principal**

Esse tipo de política geralmente usa o campo `Principal`.

Ele define a entidade autorizada.

---

## Exemplo prático

Recursos que podem usar políticas próprias incluem:

* [[Buckets S3|buckets]] [[Amazon S3]];
* chaves [[AWS Key Management Service (KMS)]];
* filas [[Amazon SQS]];
* tópicos [[Amazon SNS]];
* funções [[AWS Lambda]];
* secrets;
* outros recursos compatíveis.

Um [[Buckets S3|bucket S3]] pode ter política permitindo leitura apenas por uma role específica de uma aplicação.

Isso é mais seguro do que liberar acesso público.

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

**Diferença para Política de Identidade**

Política de identidade diz o que uma identidade pode fazer.

Política baseada em recurso diz quem pode acessar aquele recurso.

---

## Cuidados

Políticas baseadas em recurso podem expor dados se forem amplas demais.

Um erro em [[Buckets S3|bucket]] policy pode tornar dados acessíveis fora da intenção original.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

## Relação com outras notas

- [[Amazon S3]]
- [[AWS Key Management Service (KMS)]]
- [[Amazon SQS]]
- [[Amazon SNS]]
- [[AWS Lambda]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS CloudTrail]]
