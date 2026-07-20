S3 Glacier Instant Retrieval é uma classe do [[Amazon S3]] para dados raramente acessados que ainda precisam de recuperação em milissegundos.

Ela combina arquivamento com acesso imediato.

## Quando Usar

Use para:

* imagens antigas;
* arquivos regulatórios que podem ser solicitados sem aviso;
* mídia raramente acessada;
* backups que precisam de restauração rápida;
* arquivos históricos com acesso ocasional imediato.

---

## Diferença para Flexible Retrieval

[[S3 Glacier Flexible Retrieval]] pode ter recuperação em minutos ou horas.

Glacier Instant Retrieval preserva acesso imediato, com outro perfil de custo.

---

## Trade-off

É mais barato que manter tudo em classes quentes, mas não tão barato quanto classes Glacier de recuperação mais lenta.

---

## Cuidado

Não escolha apenas pelo nome “Glacier”. A diferença entre instant, flexible e deep archive muda completamente o tempo de recuperação.

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
