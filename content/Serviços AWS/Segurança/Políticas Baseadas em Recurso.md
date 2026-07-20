Políticas Baseadas em Recurso são políticas anexadas diretamente a um recurso AWS.

Elas definem quem pode acessar aquele recurso e em quais condições.

---

## Visão geral

Em Políticas Baseadas em Recurso, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Exemplos

Recursos que podem usar políticas próprias incluem:

* buckets [[Amazon S3]];
* chaves [[AWS Key Management Service (KMS)]];
* filas [[Amazon SQS]];
* tópicos [[Amazon SNS]];
* funções [[AWS Lambda]];
* secrets;
* outros recursos compatíveis.

---

## Diferença para Política de Identidade

Política de identidade diz o que uma identidade pode fazer.

Política baseada em recurso diz quem pode acessar aquele recurso.

---

## Principal

Esse tipo de política geralmente usa o campo `Principal`.

Ele define a entidade autorizada.

---

## Exemplo

Um bucket S3 pode ter política permitindo leitura apenas por uma role específica de uma aplicação.

Isso é mais seguro do que liberar acesso público.

---

## Cuidado

Políticas baseadas em recurso podem expor dados se forem amplas demais.

Um erro em bucket policy pode tornar dados acessíveis fora da intenção original.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.
