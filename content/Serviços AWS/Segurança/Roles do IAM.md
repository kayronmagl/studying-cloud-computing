Roles do [[AWS Identity and Access Management (IAM)|IAM]] são identidades assumíveis com permissões específicas.

Diferente de [[Usuários do IAM]], uma role não possui senha nem access keys permanentes próprias. Ela é assumida temporariamente por usuários, aplicações, serviços AWS ou contas externas.

Esse é um conceito central de segurança na AWS.

Em Roles do [[AWS Identity and Access Management (IAM)|IAM]], pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Roles do IAM deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

A role entrega credenciais temporárias para a instância.

A aplicação usa essas credenciais sem precisar de access keys fixas no código.

---

## Por que existe

Roles do [[AWS Identity and Access Management (IAM)|IAM]] existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Por que Roles Existem**

Roles resolvem o problema de conceder acesso sem distribuir credenciais permanentes.

Exemplos:

* uma instância [[Amazon EC2]] acessa [[Amazon S3]];
* uma função [[AWS Lambda]] grava logs no [[Amazon CloudWatch]];
* uma conta externa assume acesso limitado;
* um usuário assume uma role administrativa por tempo controlado;
* um serviço AWS executa ações em nome do cliente.

**Credenciais Temporárias**

Ao assumir uma role, a entidade recebe [[Credenciais Temporárias|credenciais temporárias]] emitidas pelo [[AWS Security Token Service (STS)]].

Essas credenciais expiram.

Isso reduz risco em comparação com access keys permanentes.

**Trust Policy**

Uma role possui uma política de confiança.

Ela define quem pode assumir a role.

Exemplo: uma role pode confiar no serviço [[AWS Lambda|Lambda]], permitindo que funções [[AWS Lambda|Lambda]] a utilizem.

**Permission Policy**

Além da confiança, a role precisa de permissões.

A política de permissão define o que a role pode fazer depois de assumida.

---

## Exemplo prático

Uma função [[AWS Lambda|Lambda]] precisa ler um [[Buckets S3|bucket S3]].

A role da função deve:

* confiar no serviço [[AWS Lambda|Lambda]]
* permitir s3: GetObject no [[Buckets S3|bucket]] necessário
* permitir logs no CloudWatch

Ela não precisa permissão para apagar bancos, criar usuários ou alterar rede.

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

**Pontos que Costumam Gerar Confusão**

Quando uma aplicação em [[Amazon EC2|EC2]] precisa acessar um [[Buckets S3|bucket]] privado [[Amazon S3|S3]], a abordagem recomendada é criar uma [[AWS Identity and Access Management (IAM)|IAM]] role com permissões apropriadas e associar à instância [[Amazon EC2|EC2]].

---

## Cuidados

**Boas Práticas**

* preferir roles para aplicações;
* usar permissões mínimas;
* evitar wildcards amplos;
* limitar quem pode assumir;
* usar condições;
* revisar roles antigas;
* monitorar uso com [[AWS CloudTrail]].

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

Não codifique chave de acesso na aplicação.

Não use [[Amazon VPC|VPC]] peering para resolver permissão de [[Amazon S3|S3]].

Acesso a [[Amazon S3|S3]] precisa de permissão [[AWS Identity and Access Management (IAM)|IAM]] adequada.

---

## Relação com outras notas

- [[Usuários do IAM]]
- [[Amazon EC2]]
- [[Amazon S3]]
- [[AWS Lambda]]
- [[Amazon CloudWatch]]
- [[Credenciais Temporárias]]
- [[AWS Security Token Service (STS)]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
