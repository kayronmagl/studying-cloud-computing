Infraestrutura como Código, ou IaC, é a prática de declarar infraestrutura em arquivos versionáveis.

Em vez de criar recursos manualmente pelo [[AWS Management Console]], a equipe descreve redes, servidores, bancos, [[Buckets S3|buckets]], permissões e alarmes em código.

Infraestrutura como Código (IaC) mostra como você conversa com a AWS. A ideia é simples: tudo que você cria, consulta ou altera precisa passar por alguma interface e por permissões.

Pense nisso como a ponte entre você, seu código e os serviços da AWS.

---

## O que é

Infraestrutura como Código é a prática de descrever infraestrutura em arquivos, em vez de criar tudo manualmente.

A ideia é tratar infraestrutura como software: versionar, revisar, repetir e automatizar.

---

## Por que existe

IaC reduz erro manual, melhora auditoria, permite revisão por versionamento e facilita recriar ambientes. Uma mesma definição pode criar [[Amazon VPC]], [[Amazon EC2]], [[Amazon RDS]], [[Amazon S3]] e alarmes do [[Amazon CloudWatch]].

Sem IaC, ambientes são criados por cliques e podem ficar diferentes entre si.

Com IaC, a equipe declara o estado desejado: [[Amazon VPC|VPC]], subnets, instâncias, [[Buckets S3|buckets]], roles, bancos e políticas.

* repetibilidade;
* versionamento;
* revisão por pull request;
* menor erro humano;
* criação rápida de ambientes;
* documentação viva da infraestrutura.

---

## Como funciona

Infraestrutura como Código (IaC) funciona enviando uma solicitação para APIs da AWS com identidade, região, parâmetros e permissões. A AWS valida a chamada, executa a operação quando autorizada e registra eventos para auditoria.

---

## Exemplo prático

Um usuário pode criar um [[Buckets S3|bucket S3]] pelo console. Um script pode criar o mesmo [[Buckets S3|bucket]] pela [[AWS CLI]]. Uma aplicação pode enviar objetos usando [[AWS SDKs|SDK]]. Um template de infraestrutura como código pode declarar o [[Buckets S3|bucket]] de forma versionada.

O serviço resultante é o mesmo, mas o método de interação muda.

Uma equipe pode criar recursos manualmente no início, mas depois declarar tudo em IaC para reproduzir ambientes. Aplicações usam [[AWS SDKs|SDKs]] para falar com [[Amazon S3|S3]], [[Amazon DynamoDB|DynamoDB]] ou [[Amazon SQS|SQS]].

---

## Diferenças importantes

Compare Infraestrutura como Código (IaC) com console, CLI, SDK, API e IaC. Console favorece exploração visual; CLI favorece terminal e scripts; SDK fica dentro da aplicação; API é a interface base; IaC descreve infraestrutura em arquivos.

---

## Cuidados

Operação manual é útil no aprendizado, mas pode gerar inconsistência em produção.

Por isso, conforme o ambiente amadurece, automação, versionamento, permissões bem definidas e auditoria com [[AWS CloudTrail]] tornam-se essenciais.

Toda interação precisa respeitar [[AWS Identity and Access Management (IAM)|IAM]], auditoria, versionamento e revisão.

Operação manual sem registro dificulta troubleshooting e governança.

IaC não garante boa arquitetura. Ele apenas torna a arquitetura repetível. Se o código declarar uma configuração insegura, ela será reproduzida com eficiência.

---

## Relação com outras notas

**Relação com Nuvem**

Como recursos de nuvem são expostos por [[APIs]], eles podem ser automatizados. IaC é a forma disciplinada de tratar infraestrutura como parte do sistema.
