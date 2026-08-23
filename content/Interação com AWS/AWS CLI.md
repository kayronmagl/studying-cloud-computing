AWS CLI é a ferramenta de linha de comando da AWS. Ela executa operações por terminal, facilitando scripts, automação e administração técnica.

AWS CLI mostra como você conversa com a AWS. A ideia é simples: tudo que você cria, consulta ou altera precisa passar por alguma interface e por permissões.

Pense nisso como a ponte entre você, seu código e os serviços da AWS.

---

## O que é

A AWS CLI é a ferramenta de linha de comando da AWS.

Ela permite executar operações em serviços AWS usando comandos no terminal.

---

## Por que existe

AWS CLI existe para explicar uma forma de criar, consultar, alterar ou automatizar recursos em nuvem. Toda interação com AWS passa por [[APIs|APIs]], permissões, auditoria e algum nível de governança.

---

## Como funciona

A CLI recebe um comando, autentica com credenciais e chama [[APIs|APIs]] da AWS.

Exemplo conceitual:

```bash
aws s3 ls
aws ec2 describe-instances
```

Esses comandos não “entram” no servidor da AWS. Eles chamam [[APIs|APIs]] autorizadas.

---

## Exemplo prático

Um usuário pode criar um [[Buckets S3|bucket S3]] pelo console. Um script pode criar o mesmo [[Buckets S3|bucket]] pela AWS CLI. Uma aplicação pode enviar objetos usando [[AWS SDKs|SDK]]. Um template de infraestrutura como código pode declarar o [[Buckets S3|bucket]] de forma versionada.

O serviço resultante é o mesmo, mas o método de interação muda.

Uma equipe pode criar recursos manualmente no início, mas depois declarar tudo em [[Infraestrutura como Código (IaC)|IaC]] para reproduzir ambientes. Aplicações usam [[AWS SDKs|SDKs]] para falar com [[Amazon S3|S3]], [[Amazon DynamoDB|DynamoDB]] ou [[Amazon SQS|SQS]].

---

## Diferenças importantes

**Quando Usar**

* scripts;
* automação;
* administração técnica;
* tarefas repetitivas;
* integração com pipelines;
* diagnóstico rápido.

---

## Cuidados

Operação manual é útil no aprendizado, mas pode gerar inconsistência em produção.

Por isso, conforme o ambiente amadurece, automação, versionamento, permissões bem definidas e auditoria com [[AWS CloudTrail]] tornam-se essenciais.

Toda interação precisa respeitar [[AWS Identity and Access Management (IAM)|IAM]], auditoria, versionamento e revisão.

Operação manual sem registro dificulta troubleshooting e governança.

CLI exige permissões [[AWS Identity and Access Management (IAM)|IAM]]. Se uma ação falha, muitas vezes o problema não é o comando, mas a falta de permissão, região errada, profile errado ou credenciais inválidas.

---

## Relação com outras notas

**Criação de recursos**

Ao usar CLI, console, [[AWS SDKs|SDK]] ou infraestrutura como código, você está fazendo [[Provisionamento]] de recursos na AWS.
