S3 Replication é o recurso do [[Amazon S3]] para copiar objetos automaticamente entre buckets.

A replicação pode ocorrer entre regiões ou dentro da mesma região, dependendo da configuração.

## Tipos

* replicação entre regiões;
* replicação na mesma região;
* replicação seletiva por prefixo, tag ou regra.

---

## Quando Usar

Use para:

* recuperação de desastres;
* residência de dados;
* cópia de segurança;
* distribuição geográfica;
* separação de ambientes;
* proteção contra falha regional em cenários específicos.

---

## Relação com Versioning

Replicação normalmente se conecta com [[S3 Versioning]].

Versionamento ajuda a preservar histórico e permite replicar alterações de objetos.

---

## Cuidado

Replicação não corrige erro lógico.

Se um objeto errado for gravado e replicado, a cópia também pode receber o erro. Para proteção contra exclusão ou sobrescrita indevida, avalie [[S3 Object Lock]] e versionamento.

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
