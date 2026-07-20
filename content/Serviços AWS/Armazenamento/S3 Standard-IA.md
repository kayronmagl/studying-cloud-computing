S3 Standard-IA significa Standard-Infrequent Access.

É uma classe do [[Amazon S3]] para dados acessados com menor frequência, mas que ainda precisam de recuperação rápida.

## Quando Usar

Use para:

* backups recentes;
* documentos antigos consultados ocasionalmente;
* arquivos de recuperação;
* dados acessados poucas vezes por mês;
* objetos que ainda precisam de acesso imediato quando solicitados.

---

## Trade-off

O custo de armazenamento é menor que S3 Standard, mas há cobrança por recuperação e requisitos mínimos de armazenamento.

Se o dado for acessado com frequência, a economia pode desaparecer.

---

## Exemplo

Relatórios mensais antigos podem ficar em Standard-IA se raramente consultados, mas ainda precisarem ser baixados rapidamente quando alguém solicitar.

---

## Cuidado

Não use Standard-IA para dados temporários de vida curta ou objetos muito acessados.

---

## Exemplo Prático

Uma aplicação pode usar:

* [[Amazon EBS]] para disco de uma instância;
* [[Amazon S3]] para objetos e arquivos;
* [[Amazon EFS]] para filesystem compartilhado;
* classes de armazenamento para reduzir custo de dados antigos.

Cada escolha muda o comportamento da aplicação.

---

## Critério de Escolha

Pergunte:


* a aplicação precisa de disco?
* precisa de API de objeto?
* precisa compartilhar arquivos entre máquinas?
* precisa arquivar por anos?
* precisa recuperar imediatamente?


Responder essas perguntas evita usar S3 como se fosse disco, EBS como se fosse compartilhado, ou EFS como se fosse banco.

---

## Como entender isso

Este conceito pertence ao [[Amazon S3]], serviço de armazenamento de objetos.

## Ponto central

S3 trabalha com buckets e objetos. Ele é acessado por API e é usado para arquivos, imagens, logs, backups, data lakes e conteúdo estático.

## Como Diferenciar

* S3 não é disco de EC2.
* Bucket precisa de política, criptografia e bloqueio de acesso público quando necessário.
* Classes de armazenamento mudam custo e padrão de acesso.
* Lifecycle automatiza movimentação e expiração.
* Versioning ajuda a recuperar sobrescritas e exclusões.

## Cuidado importante

S3 pode parecer uma pasta, mas internamente trabalha com objetos identificados por chaves.
