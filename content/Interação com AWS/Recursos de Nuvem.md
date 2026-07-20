Recursos de Nuvem são unidades configuráveis, como instâncias, buckets, bancos, redes, funções e alarmes. Cada recurso possui custo, permissões, escopo e ciclo de vida.

---

## Visão geral

Recursos de Nuvem mostra como você conversa com a AWS. A ideia é simples: tudo que você cria, consulta ou altera precisa passar por alguma interface e por permissões.

Pense nisso como a ponte entre você, seu código e os serviços da AWS.

---

## Exemplo Prático

Um usuário pode criar um bucket S3 pelo console. Um script pode criar o mesmo bucket pela AWS CLI. Uma aplicação pode enviar objetos usando SDK. Um template de infraestrutura como código pode declarar o bucket de forma versionada.

O serviço resultante é o mesmo, mas o método de interação muda.

---

## Cuidados importantes

Operação manual é útil no aprendizado, mas pode gerar inconsistência em produção.

Por isso, conforme o ambiente amadurece, automação, versionamento, permissões bem definidas e auditoria com [[AWS CloudTrail]] tornam-se essenciais.

---

## Exemplo Arquitetural

Uma equipe pode criar recursos manualmente no início, mas depois declarar tudo em IaC para reproduzir ambientes. Aplicações usam SDKs para falar com S3, DynamoDB ou SQS.

---

## Cuidado adicional

Toda interação precisa respeitar IAM, auditoria, versionamento e revisão.

Operação manual sem registro dificulta troubleshooting e governança.
