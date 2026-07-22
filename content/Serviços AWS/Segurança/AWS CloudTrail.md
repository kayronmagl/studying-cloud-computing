AWS CloudTrail é o serviço da AWS que registra chamadas de API e eventos de atividade da conta.

Ele responde perguntas como:


* quem fez?
* o que fez?
* quando fez?
* de onde fez?
* em qual recurso?



Em AWS CloudTrail, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Por que é Essencial

Quase toda ação na AWS passa por API.

Mesmo cliques no console geram chamadas de API.

CloudTrail registra essas atividades e permite auditoria, investigação e conformidade.

---

## Exemplos

CloudTrail pode registrar:

* criação de instância EC2;
* alteração de política IAM;
* leitura de secret;
* criação de bucket;
* exclusão de recurso;
* assume role;
* mudanças em security groups.

---

## Relação com Segurança

Sem CloudTrail, investigar incidentes fica muito mais difícil.

Ele é uma das primeiras coisas que devem estar habilitadas e protegidas em contas reais.

---

## Cuidado

Logs também precisam ser protegidos.

Uma conta comprometida não deve conseguir apagar evidências facilmente.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

## Explicação principal

AWS CloudTrail registra chamadas de API e eventos de conta.

Ele responde: quem fez o quê, quando, de onde e em qual recurso.

## Diferença para CloudWatch

CloudWatch monitora métricas e logs operacionais.

CloudTrail registra auditoria de ações na AWS.

## Usos

* investigação de incidente;
* auditoria;
* conformidade;
* rastrear alterações;
* detectar uso indevido de credenciais.

## Cuidado importante

CloudTrail não é ferramenta de performance. Ele não diz se a aplicação está lenta; ele mostra ações feitas na conta.

---

## Pontos que Costumam Gerar Confusão

Quando o cenário envolve revisar detalhes de atividades de usuário e chamadas de API no ambiente AWS, a resposta é [[AWS CloudTrail]].

---

## Como entender

CloudTrail é auditoria.

Ele registra ações feitas na conta:


* quem fez
* o quê
* quando
* de onde
* em qual recurso


---

## Diferença para CloudWatch na prática

* CloudTrail: auditoria de API.
* [[Amazon CloudWatch|CloudWatch]]: métricas, logs e alarmes operacionais.


---

## Na prática

CloudTrail é o histórico de ações na sua conta AWS.

Ele ajuda a responder: quem fez o quê?

---

## Exemplo

Alguém alterou uma política IAM ou apagou um recurso.

Com CloudTrail, você procura a chamada de API e vê usuário, horário, origem e ação realizada.

---

## Como Diferenciar

Procure frases como:


* atividade de usuário
* chamadas de API
* auditoria
* quem fez o quê


A resposta é AWS CloudTrail.

---

## CloudTrail vs CloudWatch

* CloudTrail: auditoria e chamadas de API.
* [[Amazon CloudWatch|CloudWatch]]: métricas, logs e alarmes.


Quando o cenário envolve monitoramento de performance, é CloudWatch.

Se fala em atividade de usuário/API, é CloudTrail.
