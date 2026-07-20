Classes de Armazenamento do Amazon S3 definem como objetos são armazenados em termos de custo, disponibilidade, frequência de acesso e tempo de recuperação.

Cada objeto no S3 possui uma classe de armazenamento. Se nenhuma classe for especificada, o padrão é [[S3 Standard]].

## Por que Existem

Nem todo dado precisa do mesmo nível de acesso.

Um arquivo usado todos os dias precisa de acesso imediato. Um backup antigo pode aceitar restauração mais lenta. Um log regulatório pode ficar guardado por anos sem consulta frequente.

As classes permitem alinhar custo ao valor operacional do dado.

---

## Classes Principais

* [[S3 Standard]];
* [[S3 Intelligent-Tiering]];
* [[S3 Standard-IA]];
* [[S3 One Zone-IA]];
* [[S3 Glacier Instant Retrieval]];
* [[S3 Glacier Flexible Retrieval]];
* [[S3 Glacier Deep Archive]].

---

## Critérios de Escolha

Considere frequência de acesso, tempo de recuperação, custo de armazenamento, custo de recuperação, duração mínima, resiliência, conformidade e criticidade.

---

## Lifecycle

[[S3 Lifecycle]] automatiza transição entre classes.

Isso conecta arquitetura técnica com governança e custo.

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
