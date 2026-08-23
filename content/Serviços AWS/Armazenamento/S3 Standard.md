[[Amazon S3|S3]] Standard é a classe padrão do [[Amazon S3]] para dados acessados com frequência.

Ela é indicada para objetos ativos, como imagens recentes, arquivos estáticos, documentos frequentemente acessados, logs recentes e conteúdo distribuído por [[Amazon CloudFront]].

---

## O que é

S3 Standard deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

[[Amazon S3|S3]] trabalha com [[Buckets S3|buckets]] e objetos. Ele é acessado por [[APIs|API]] e é usado para arquivos, imagens, logs, backups, data lakes e conteúdo estático.

---

## Por que existe

[[Amazon S3|S3]] Standard existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**Migração**

Quando os objetos envelhecem e passam a ser acessados raramente, [[S3 Lifecycle]] pode movê-los para [[S3 Standard-IA]], [[S3 Intelligent-Tiering]] ou classes Glacier.

---

## Exemplo prático

* imagens de produtos atuais;
* arquivos de sites;
* documentos usados diariamente;
* exports recentes;
* dados de aplicações ativas.

Uma aplicação pode usar:

* [[Amazon EBS]] para disco de uma instância;
* [[Amazon S3]] para objetos e arquivos;
* [[Amazon EFS]] para filesystem compartilhado;
* classes de armazenamento para reduzir custo de dados antigos.

Cada escolha muda o comportamento da aplicação.

---

## Diferenças importantes

**Quando Usar**

Use quando:

* os dados são acessados frequentemente;
* o padrão de acesso ainda é desconhecido;
* a aplicação precisa de acesso imediato;
* o objeto faz parte do fluxo operacional atual.

**Trade-off**

[[Amazon S3|S3]] Standard tende a ter custo de armazenamento maior do que classes frias, mas evita custos e atrasos de recuperação associados a classes de acesso infrequente ou arquivamento.

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

[[Amazon S3|S3]] pode parecer uma pasta, mas internamente trabalha com objetos identificados por chaves.

---

## Relação com outras notas

- [[Amazon S3]]
- [[Amazon CloudFront]]
- [[S3 Lifecycle]]
- [[S3 Standard-IA]]
- [[S3 Intelligent-Tiering]]
- [[Amazon EBS]]
- [[Amazon EFS]]
