AWS SDKs são bibliotecas oficiais para linguagens como Python, JavaScript, Java, Go e C#. Elas permitem que aplicações chamem serviços como [[Amazon S3]], [[AWS Lambda]] e [[Amazon DynamoDB]].


AWS SDKs mostra como você conversa com a AWS. A ideia é simples: tudo que você cria, consulta ou altera precisa passar por alguma interface e por permissões.

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

## Exemplo

Uma equipe pode criar recursos manualmente no início, mas depois declarar tudo em IaC para reproduzir ambientes. Aplicações usam SDKs para falar com S3, DynamoDB ou SQS.

---

## Cuidado adicional

Toda interação precisa respeitar IAM, auditoria, versionamento e revisão.

Operação manual sem registro dificulta troubleshooting e governança.

## Explicação principal

AWS SDKs são bibliotecas oficiais para aplicações conversarem com serviços AWS usando linguagens de programação.

Em vez de uma pessoa digitar comandos, o próprio código chama serviços como S3, DynamoDB, SQS ou Lambda.

## Exemplo

Uma aplicação Python pode usar SDK para enviar arquivo ao S3.

Uma aplicação Node.js pode publicar mensagem no SQS.

Um backend Java pode consultar DynamoDB.

## Diferença para CLI

A CLI é usada por humanos e scripts.

SDKs são usados dentro de aplicações.

Ambos chamam APIs da AWS.

## Cuidado importante

SDK não dispensa IAM. A aplicação precisa de credenciais ou role com permissões adequadas. Em EC2, usa-se geralmente role de instância; em Lambda, role de execução.
