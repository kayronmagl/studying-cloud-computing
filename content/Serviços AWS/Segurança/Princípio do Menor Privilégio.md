O Princípio do Menor Privilégio determina que uma identidade deve receber apenas as permissões necessárias para executar sua função, nada além disso.

Esse princípio é central em [[AWS Identity and Access Management (IAM)]].

Em Princípio do Menor Privilégio, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Princípio do Menor Privilégio deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

Não dê acesso amplo “por garantia”.

Dê apenas o necessário para a pessoa, aplicação ou serviço cumprir a função.

---

## Por que existe

Permissões amplas aumentam impacto de erro, vazamento de credencial ou invasão.

Se uma função [[AWS Lambda|Lambda]] só precisa ler um [[Buckets S3|bucket]], ela não deve poder apagar [[Buckets S3|buckets]], criar usuários ou modificar redes.

---

## Como funciona

**Exemplo Ruim**

* Action: "*"
* Resource: "*"

Isso concede acesso amplo demais.

**Exemplo Melhor**

* Action: s3: GetObject
* Resource: arn:aws:s3:::[[Buckets S3|bucket]]-da-aplicacao/*

Essa permissão é específica.

**Como Aplicar**

* começar com permissões mínimas;
* usar políticas específicas;
* restringir recursos;
* usar condições;
* revisar acessos;
* remover permissões sem uso;
* usar roles temporárias;
* monitorar com [[AWS CloudTrail]].

---

## Exemplo prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

**Trade-off**

Permissões mínimas podem exigir mais trabalho inicial.

Mas reduzem risco operacional e melhoram governança.

**Como Diferenciar**

* [[AWS Identity and Access Management (IAM)|IAM]] controla permissões.
* KMS gerencia chaves.
* WAF filtra HTTP/HTTPS.
* Shield protege contra DDoS.
* CloudTrail audita chamadas de [[APIs|API]].
* GuardDuty detecta ameaças.

**Pontos que Costumam Gerar Confusão**

A melhor prática de [[AWS Identity and Access Management (IAM)|IAM]] cobrada foi conceder permissões apenas a usuários que precisam executar uma tarefa específica.

Isso é o [[Princípio do Menor Privilégio]].

---

## Cuidados

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

Gerar chaves secretas para todo usuário não é melhor prática.

Armazenar credenciais em [[Amazon EC2|EC2]] também não é.

O ideal é usar roles, permissões mínimas e credenciais temporárias sempre que possível.

---

## Relação com outras notas

- [[AWS Identity and Access Management (IAM)]]
- [[AWS CloudTrail]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Key Management Service (KMS)]]
