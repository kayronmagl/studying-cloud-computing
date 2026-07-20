S3 Glacier Flexible Retrieval é uma classe do [[Amazon S3]] para arquivamento de baixo custo com recuperação flexível.

A recuperação pode levar de minutos a horas, dependendo da opção escolhida.

## Quando Usar

Use para:

* backups;
* arquivos históricos;
* auditoria;
* retenção de longo prazo;
* dados raramente acessados;
* arquivos que podem esperar restauração.

---

## Trade-off

* menor custo de armazenamento: ↓.
* maior tempo de recuperação


---

## Exemplo

Backups antigos que raramente precisam ser restaurados podem usar Flexible Retrieval se o negócio tolera aguardar a recuperação.

---

## Cuidado

Não use para dados operacionais que precisam estar disponíveis imediatamente.

Antes de escolher, confirme RTO e RPO do workload.

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
