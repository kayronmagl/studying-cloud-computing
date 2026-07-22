Roles do IAM são identidades assumíveis com permissões específicas.

Diferente de [[Usuários do IAM]], uma role não possui senha nem access keys permanentes próprias. Ela é assumida temporariamente por usuários, aplicações, serviços AWS ou contas externas.

Esse é um conceito central de segurança na AWS.


Em Roles do IAM, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Por que Roles Existem

Roles resolvem o problema de conceder acesso sem distribuir credenciais permanentes.

Exemplos:

* uma instância [[Amazon EC2]] acessa [[Amazon S3]];
* uma função [[AWS Lambda]] grava logs no [[Amazon CloudWatch]];
* uma conta externa assume acesso limitado;
* um usuário assume uma role administrativa por tempo controlado;
* um serviço AWS executa ações em nome do cliente.

---

## Credenciais Temporárias

Ao assumir uma role, a entidade recebe [[Credenciais Temporárias|credenciais temporárias]] emitidas pelo [[AWS Security Token Service (STS)]].

Essas credenciais expiram.

Isso reduz risco em comparação com access keys permanentes.

---

## Trust Policy

Uma role possui uma política de confiança.

Ela define quem pode assumir a role.

Exemplo: uma role pode confiar no serviço Lambda, permitindo que funções Lambda a utilizem.

---

## Permission Policy

Além da confiança, a role precisa de permissões.

A política de permissão define o que a role pode fazer depois de assumida.

---

## Exemplo

Uma função Lambda precisa ler um bucket S3.

A role da função deve:


* confiar no serviço Lambda
* permitir s3: GetObject no bucket necessário
* permitir logs no CloudWatch


Ela não precisa permissão para apagar bancos, criar usuários ou alterar rede.

---

## Boas Práticas

* preferir roles para aplicações;
* usar permissões mínimas;
* evitar wildcards amplos;
* limitar quem pode assumir;
* usar condições;
* revisar roles antigas;
* monitorar uso com [[AWS CloudTrail]].

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

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

---

## Pontos que Costumam Gerar Confusão

Quando uma aplicação em EC2 precisa acessar um bucket privado S3, a abordagem recomendada é criar uma IAM role com permissões apropriadas e associar à instância EC2.

---

## Como entender

A role entrega credenciais temporárias para a instância.

A aplicação usa essas credenciais sem precisar de access keys fixas no código.

---

## Cuidado importante na prática

Não codifique chave de acesso na aplicação.

Não use VPC peering para resolver permissão de S3.

Acesso a S3 precisa de permissão IAM adequada.
