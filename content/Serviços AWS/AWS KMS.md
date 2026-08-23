AWS KMS é o nome curto de [[AWS Key Management Service (KMS)]], o serviço da AWS para criar, gerenciar e usar chaves criptográficas.

Ele protege dados em serviços AWS e aplicações, combinando criptografia, controle de acesso e auditoria.

---

## O que é

AWS KMS permite controlar chaves usadas para criptografar e descriptografar dados.

Ele não serve apenas para guardar chaves. Ele também define quem pode usar uma chave, em quais condições e com registro de auditoria.

---

## Por que existe

Sem um serviço central de chaves, cada aplicação ou serviço precisaria administrar criptografia de forma própria.

Isso aumentaria risco de vazamento, perda de chave, configuração inconsistente e falta de rastreabilidade.

---

## Como funciona

Serviços como [[Amazon S3]], [[Amazon EBS]], [[Amazon RDS]] e [[AWS CloudTrail]] podem usar chaves do KMS para proteger dados em repouso.

O acesso depende de permissões do [[AWS Identity and Access Management (IAM)|IAM]] e de políticas da própria chave.

---

## Exemplo prático

Um [[Buckets S3|bucket S3]] pode armazenar objetos criptografados com uma chave KMS.

Mesmo que uma identidade tenha permissão para acessar o [[Buckets S3|bucket]], ela também precisa ter permissão adequada para usar a chave quando a operação exigir descriptografia.

---

## Diferenças importantes

[[AWS Identity and Access Management (IAM)|IAM]] controla permissões de identidade.

KMS controla chaves criptográficas e o uso dessas chaves.

Criptografia em repouso protege dados armazenados; criptografia em trânsito protege dados durante comunicação.

---

## Cuidados

Criptografia não substitui permissão correta.

Uma chave mal configurada pode bloquear uma aplicação legítima ou liberar acesso além do necessário.

Permissões de KMS devem seguir o [[Princípio do Menor Privilégio]] e precisam ser auditáveis com [[AWS CloudTrail]].

---

## Relação com outras notas

- [[AWS Key Management Service (KMS)]]
- [[Chaves KMS]]
- [[Criptografia em Repouso]]
- [[Criptografia em Trânsito]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS CloudTrail]]
