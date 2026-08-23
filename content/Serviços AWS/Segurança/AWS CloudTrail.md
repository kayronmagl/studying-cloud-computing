AWS CloudTrail é o serviço da AWS que registra chamadas de [[APIs|API]] e eventos de atividade da conta.

Ele responde perguntas como:

* quem fez?
* o que fez?
* quando fez?
* de onde fez?
* em qual recurso?

Em AWS CloudTrail, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

AWS CloudTrail registra chamadas de [[APIs|API]] e eventos de conta.

Ele responde: quem fez o quê, quando, de onde e em qual recurso.

CloudTrail é auditoria.

Ele registra ações feitas na conta:

* quem fez
* o quê
* quando
* de onde
* em qual recurso

---

## Por que existe

AWS CloudTrail existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Por que é Essencial**

Quase toda ação na AWS passa por [[APIs|API]].

Mesmo cliques no console geram chamadas de [[APIs|API]].

CloudTrail registra essas atividades e permite auditoria, investigação e conformidade.

**Usos**

* investigação de incidente;
* auditoria;
* conformidade;
* rastrear alterações;
* detectar uso indevido de credenciais.

**Na prática**

CloudTrail é o histórico de ações na sua conta AWS.

Ele ajuda a responder: quem fez o quê?

**CloudTrail vs CloudWatch**

* CloudTrail: auditoria e chamadas de [[APIs|API]].
* [[Amazon CloudWatch|CloudWatch]]: métricas, logs e alarmes.

Quando o cenário envolve monitoramento de performance, é CloudWatch.

Se fala em atividade de usuário/[[APIs|API]], é CloudTrail.

---

## Exemplo prático

CloudTrail pode registrar:

* criação de instância [[Amazon EC2|EC2]];
* alteração de política [[AWS Identity and Access Management (IAM)|IAM]];
* leitura de secret;
* criação de [[Buckets S3|bucket]];
* exclusão de recurso;
* assume role;
* mudanças em security groups.

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

Alguém alterou uma política [[AWS Identity and Access Management (IAM)|IAM]] ou apagou um recurso.

Com CloudTrail, você procura a chamada de [[APIs|API]] e vê usuário, horário, origem e ação realizada.

---

## Diferenças importantes

**Diferença para CloudWatch**

CloudWatch monitora métricas e logs operacionais.

CloudTrail registra auditoria de ações na AWS.

**Pontos que Costumam Gerar Confusão**

Quando o cenário envolve revisar detalhes de atividades de usuário e chamadas de [[APIs|API]] no ambiente AWS, a resposta é [[AWS CloudTrail]].

**Diferença para CloudWatch na prática**

* CloudTrail: auditoria de [[APIs|API]].
* [[Amazon CloudWatch|CloudWatch]]: métricas, logs e alarmes operacionais.

**Como Diferenciar**

Procure frases como:

* atividade de usuário
* chamadas de [[APIs|API]]
* auditoria
* quem fez o quê

A resposta é AWS CloudTrail.

---

## Cuidados

Logs também precisam ser protegidos.

Uma conta comprometida não deve conseguir apagar evidências facilmente.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

CloudTrail não é ferramenta de performance. Ele não diz se a aplicação está lenta; ele mostra ações feitas na conta.

---

## Relação com outras notas

**Relação com Segurança**

Sem CloudTrail, investigar incidentes fica muito mais difícil.

Ele é uma das primeiras coisas que devem estar habilitadas e protegidas em contas reais.

- [[Amazon CloudWatch]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
