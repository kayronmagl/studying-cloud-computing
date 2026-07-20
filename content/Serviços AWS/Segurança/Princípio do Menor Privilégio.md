O Princípio do Menor Privilégio determina que uma identidade deve receber apenas as permissões necessárias para executar sua função, nada além disso.

Esse princípio é central em [[AWS Identity and Access Management (IAM)]].

---

## Visão geral

Em Princípio do Menor Privilégio, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Por que Importa

Permissões amplas aumentam impacto de erro, vazamento de credencial ou invasão.

Se uma função Lambda só precisa ler um bucket, ela não deve poder apagar buckets, criar usuários ou modificar redes.

---

## Exemplo Ruim

* Action: "*"
* Resource: "*"


Isso concede acesso amplo demais.

---

## Exemplo Melhor

* Action: s3: GetObject
* Resource: arn:aws:s3:::bucket-da-aplicacao/*


Essa permissão é específica.

---

## Como Aplicar

* começar com permissões mínimas;
* usar políticas específicas;
* restringir recursos;
* usar condições;
* revisar acessos;
* remover permissões sem uso;
* usar roles temporárias;
* monitorar com [[AWS CloudTrail]].

---

## Trade-off

Permissões mínimas podem exigir mais trabalho inicial.

Mas reduzem risco operacional e melhoram governança.

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

---

## Pontos que Costumam Gerar Confusão

A melhor prática de IAM cobrada foi conceder permissões apenas a usuários que precisam executar uma tarefa específica.

Isso é o [[Princípio do Menor Privilégio]].

---

## Como entender

Não dê acesso amplo “por garantia”.

Dê apenas o necessário para a pessoa, aplicação ou serviço cumprir a função.

---

## Cuidado importante na prática

Gerar chaves secretas para todo usuário não é melhor prática.

Armazenar credenciais em EC2 também não é.

O ideal é usar roles, permissões mínimas e credenciais temporárias sempre que possível.
