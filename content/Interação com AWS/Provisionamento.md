Provisionamento é criar e configurar recursos como instâncias, [[Buckets S3|buckets]], bancos, redes e permissões. Pode ser manual ou automatizado com [[Infraestrutura como Código (IaC)]].

Provisionamento mostra como você conversa com a AWS. A ideia é simples: tudo que você cria, consulta ou altera precisa passar por alguma interface e por permissões.

Pense nisso como a ponte entre você, seu código e os serviços da AWS.

---

## O que é

Provisionamento deve ser entendido como uma forma de conversar com a AWS. A interação pode acontecer por console, CLI, SDK, API ou infraestrutura como código, mas sempre passa por permissão e registro.

---

## Por que existe

Provisionamento existe para explicar uma forma de criar, consultar, alterar ou automatizar recursos em nuvem. Toda interação com AWS passa por [[APIs|APIs]], permissões, auditoria e algum nível de governança.

---

## Como funciona

Provisionamento funciona enviando uma solicitação para APIs da AWS com identidade, região, parâmetros e permissões. A AWS valida a chamada, executa a operação quando autorizada e registra eventos para auditoria.

---

## Exemplo prático

Um usuário pode criar um [[Buckets S3|bucket S3]] pelo console. Um script pode criar o mesmo [[Buckets S3|bucket]] pela [[AWS CLI]]. Uma aplicação pode enviar objetos usando [[AWS SDKs|SDK]]. Um template de infraestrutura como código pode declarar o [[Buckets S3|bucket]] de forma versionada.

O serviço resultante é o mesmo, mas o método de interação muda.

Uma equipe pode criar recursos manualmente no início, mas depois declarar tudo em [[Infraestrutura como Código (IaC)|IaC]] para reproduzir ambientes. Aplicações usam [[AWS SDKs|SDKs]] para falar com [[Amazon S3|S3]], [[Amazon DynamoDB|DynamoDB]] ou [[Amazon SQS|SQS]].

---

## Diferenças importantes

Compare Provisionamento com console, CLI, SDK, API e IaC. Console favorece exploração visual; CLI favorece terminal e scripts; SDK fica dentro da aplicação; API é a interface base; IaC descreve infraestrutura em arquivos.

---

## Cuidados

Operação manual é útil no aprendizado, mas pode gerar inconsistência em produção.

Por isso, conforme o ambiente amadurece, automação, versionamento, permissões bem definidas e auditoria com [[AWS CloudTrail]] tornam-se essenciais.

Toda interação precisa respeitar [[AWS Identity and Access Management (IAM)|IAM]], auditoria, versionamento e revisão.

Operação manual sem registro dificulta troubleshooting e governança.

---

## Relação com outras notas

- [[Infraestrutura como Código (IaC)]]
- [[AWS CloudTrail]]
