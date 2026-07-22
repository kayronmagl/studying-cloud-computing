AWS CLI é a ferramenta de linha de comando da AWS. Ela executa operações por terminal, facilitando scripts, automação e administração técnica.


AWS CLI mostra como você conversa com a AWS. A ideia é simples: tudo que você cria, consulta ou altera precisa passar por alguma interface e por permissões.

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

## Como entender isso

A AWS CLI é a ferramenta de linha de comando da AWS.

Ela permite executar operações em serviços AWS usando comandos no terminal.

## Como Funciona

A CLI recebe um comando, autentica com credenciais e chama APIs da AWS.

Exemplo conceitual:

```bash
aws s3 ls
aws ec2 describe-instances
```

Esses comandos não “entram” no servidor da AWS. Eles chamam APIs autorizadas.

## Quando Usar

* scripts;
* automação;
* administração técnica;
* tarefas repetitivas;
* integração com pipelines;
* diagnóstico rápido.

## Cuidado importante

CLI exige permissões IAM. Se uma ação falha, muitas vezes o problema não é o comando, mas a falta de permissão, região errada, profile errado ou credenciais inválidas.

---

## Criação de recursos

Ao usar CLI, console, SDK ou infraestrutura como código, você está fazendo [[Provisionamento]] de recursos na AWS.
