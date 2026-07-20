Infraestrutura como Código, ou IaC, é a prática de declarar infraestrutura em arquivos versionáveis.

Em vez de criar recursos manualmente pelo [[AWS Management Console]], a equipe descreve redes, servidores, bancos, buckets, permissões e alarmes em código.

---

## Visão geral

Infraestrutura como Código (IaC) mostra como você conversa com a AWS. A ideia é simples: tudo que você cria, consulta ou altera precisa passar por alguma interface e por permissões.

Pense nisso como a ponte entre você, seu código e os serviços da AWS.

---

## Benefício

IaC reduz erro manual, melhora auditoria, permite revisão por versionamento e facilita recriar ambientes. Uma mesma definição pode criar [[Amazon VPC]], [[Amazon EC2]], [[Amazon RDS]], [[Amazon S3]] e alarmes do [[Amazon CloudWatch]].

---

## Relação com Nuvem

Como recursos de nuvem são expostos por [[APIs]], eles podem ser automatizados. IaC é a forma disciplinada de tratar infraestrutura como parte do sistema.

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

## Explicação principal

Infraestrutura como Código é a prática de descrever infraestrutura em arquivos, em vez de criar tudo manualmente.

A ideia é tratar infraestrutura como software: versionar, revisar, repetir e automatizar.

## Por que Importa

Sem IaC, ambientes são criados por cliques e podem ficar diferentes entre si.

Com IaC, a equipe declara o estado desejado: VPC, subnets, instâncias, buckets, roles, bancos e políticas.

## Benefícios

* repetibilidade;
* versionamento;
* revisão por pull request;
* menor erro humano;
* criação rápida de ambientes;
* documentação viva da infraestrutura.

## Cuidado importante

IaC não garante boa arquitetura. Ele apenas torna a arquitetura repetível. Se o código declarar uma configuração insegura, ela será reproduzida com eficiência.
