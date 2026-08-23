[[Amazon S3|S3]] Glacier Deep Archive é uma classe do [[Amazon S3]] voltada para retenção de longo prazo com custo muito baixo.

É usada quando os dados quase nunca são acessados e podem esperar muitas horas para recuperação.

---

## O que é

S3 Glacier Deep Archive deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

[[Amazon S3|S3]] trabalha com [[Buckets S3|buckets]] e objetos. Ele é acessado por [[APIs|API]] e é usado para arquivos, imagens, logs, backups, data lakes e conteúdo estático.

---

## Por que existe

[[Amazon S3|S3]] Glacier Deep Archive existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

O funcionamento depende do tipo de dado, padrão de acesso, necessidade de durabilidade, performance, retenção e recuperação. Ao estudar [[Amazon S3|S3]] Glacier Deep Archive, conecte capacidade, acesso, proteção, ciclo de vida e custo.

---

## Exemplo prático

Uma empresa precisa guardar documentos por anos para auditoria, mas raramente consulta esses arquivos. Deep Archive pode ser adequado.

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

* retenção fiscal;
* arquivos regulatórios antigos;
* backups de longo prazo;
* substituição de fitas;
* dados históricos;
* arquivos preservados por obrigação, não por uso operacional diário.

**Trade-off**

Deep Archive reduz custo de armazenamento, mas aumenta tempo de recuperação.

Ele é adequado quando o objetivo é preservação, não acesso rápido.

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

Não use para logs recentes, dados de produção ativos, conteúdo de aplicação ou backups que precisam restauração rápida.

[[Amazon S3|S3]] pode parecer uma pasta, mas internamente trabalha com objetos identificados por chaves.

---

## Relação com outras notas

- [[Amazon S3]]
- [[Amazon EBS]]
- [[Amazon EFS]]
