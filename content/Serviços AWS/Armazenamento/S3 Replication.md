[[Amazon S3|S3]] Replication é o recurso do [[Amazon S3]] para copiar objetos automaticamente entre [[Buckets S3|buckets]].

A replicação pode ocorrer entre regiões ou dentro da mesma região, dependendo da configuração.

---

## O que é

S3 Replication deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

[[Amazon S3|S3]] trabalha com [[Buckets S3|buckets]] e objetos. Ele é acessado por [[APIs|API]] e é usado para arquivos, imagens, logs, backups, data lakes e conteúdo estático.

---

## Por que existe

[[Amazon S3|S3]] Replication existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**Tipos**

* replicação entre regiões;
* replicação na mesma região;
* replicação seletiva por prefixo, tag ou regra.

---

## Exemplo prático

Uma aplicação pode usar:

* [[Amazon EBS]] para disco de uma instância;
* [[Amazon S3]] para objetos e arquivos;
* [[Amazon EFS]] para filesystem compartilhado;
* classes de armazenamento para reduzir custo de dados antigos.

Cada escolha muda o comportamento da aplicação.

---

## Diferenças importantes

**Quando Usar**

Use para:

* recuperação de desastres;
* residência de dados;
* cópia de segurança;
* distribuição geográfica;
* separação de ambientes;
* proteção contra falha regional em cenários específicos.

**Critério de Escolha**

Pergunte:

* a aplicação precisa de disco?
* precisa de [[APIs|API]] de objeto?
* precisa compartilhar arquivos entre máquinas?
* precisa arquivar por anos?
* precisa recuperar imediatamente?

Responder essas perguntas evita usar [[Amazon S3|S3]] como se fosse disco, EBS como se fosse compartilhado, ou EFS como se fosse banco.

**Como Diferenciar**

* [[Amazon S3|S3]] não é disco de [[Amazon EC2|EC2]].
* Bucket precisa de política, criptografia e bloqueio de acesso público quando necessário.
* Classes de armazenamento mudam custo e padrão de acesso.
* Lifecycle automatiza movimentação e expiração.
* Versioning ajuda a recuperar sobrescritas e exclusões.

---

## Cuidados

Replicação não corrige erro lógico.

Se um objeto errado for gravado e replicado, a cópia também pode receber o erro. Para proteção contra exclusão ou sobrescrita indevida, avalie [[S3 Object Lock]] e versionamento.

[[Amazon S3|S3]] pode parecer uma pasta, mas internamente trabalha com objetos identificados por chaves.

---

## Relação com outras notas

**Relação com Versioning**

Replicação normalmente se conecta com [[S3 Versioning]].

Versionamento ajuda a preservar histórico e permite replicar alterações de objetos.
