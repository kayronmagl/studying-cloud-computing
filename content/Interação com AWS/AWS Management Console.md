AWS Management Console é a interface web da AWS. Permite criar, configurar e monitorar recursos pelo navegador. É útil para aprendizado e operação manual, mas deve ser combinado com automação em ambientes maduros.

AWS Management Console mostra como você conversa com a AWS. A ideia é simples: tudo que você cria, consulta ou altera precisa passar por alguma interface e por permissões.

Pense nisso como a ponte entre você, seu código e os serviços da AWS.

---

## O que é

O AWS Management Console é a interface web usada para administrar serviços AWS pelo navegador.

Ele é útil para aprendizado e operação manual, mas não é a forma mais segura ou repetível para ambientes grandes.

---

## Por que existe

AWS Management Console existe para explicar uma forma de criar, consultar, alterar ou automatizar recursos em nuvem. Toda interação com AWS passa por [[APIs|APIs]], permissões, auditoria e algum nível de governança.

---

## Como funciona

O usuário acessa o console, autentica-se e executa ações nos serviços. Por trás da interface, a AWS chama [[APIs|APIs]].

Exemplo: quando você cria um [[Buckets S3|bucket S3]] pelo console, a ação real é uma chamada de [[APIs|API]] para o serviço [[Amazon S3|S3]].

---

## Exemplo prático

Um usuário pode criar um [[Buckets S3|bucket S3]] pelo console. Um script pode criar o mesmo [[Buckets S3|bucket]] pela [[AWS CLI]]. Uma aplicação pode enviar objetos usando [[AWS SDKs|SDK]]. Um template de infraestrutura como código pode declarar o [[Buckets S3|bucket]] de forma versionada.

O serviço resultante é o mesmo, mas o método de interação muda.

Uma equipe pode criar recursos manualmente no início, mas depois declarar tudo em [[Infraestrutura como Código (IaC)|IaC]] para reproduzir ambientes. Aplicações usam [[AWS SDKs|SDKs]] para falar com [[Amazon S3|S3]], [[Amazon DynamoDB|DynamoDB]] ou [[Amazon SQS|SQS]].

---

## Diferenças importantes

**Quando Usar**

* estudo e laboratórios;
* visualização de recursos;
* troubleshooting rápido;
* configuração manual inicial;
* aprendizado de serviços.

---

## Cuidados

Operação manual é útil no aprendizado, mas pode gerar inconsistência em produção.

Por isso, conforme o ambiente amadurece, automação, versionamento, permissões bem definidas e auditoria com [[AWS CloudTrail]] tornam-se essenciais.

Toda interação precisa respeitar [[AWS Identity and Access Management (IAM)|IAM]], auditoria, versionamento e revisão.

Operação manual sem registro dificulta troubleshooting e governança.

Console não é sinônimo de automação. Em produção, é comum usar [[AWS CLI]], [[AWS SDKs]] ou [[Infraestrutura como Código (IaC)]] para reduzir erro humano e padronizar ambientes.

---

## Relação com outras notas

- [[AWS CloudTrail]]
- [[AWS CLI]]
- [[AWS SDKs]]
- [[Infraestrutura como Código (IaC)]]
