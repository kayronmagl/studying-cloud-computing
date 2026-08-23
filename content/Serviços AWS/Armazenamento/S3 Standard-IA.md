[[Amazon S3|S3]] Standard-IA significa Standard-Infrequent Access.

É uma classe do [[Amazon S3]] para dados acessados com menor frequência, mas que ainda precisam de recuperação rápida.

---

## O que é

S3 Standard-IA deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

[[Amazon S3|S3]] trabalha com [[Buckets S3|buckets]] e objetos. Ele é acessado por [[APIs|API]] e é usado para arquivos, imagens, logs, backups, data lakes e conteúdo estático.

---

## Por que existe

[[Amazon S3|S3]] Standard-IA existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

O funcionamento depende do tipo de dado, padrão de acesso, necessidade de durabilidade, performance, retenção e recuperação. Ao estudar [[Amazon S3|S3]] Standard-IA, conecte capacidade, acesso, proteção, ciclo de vida e custo.

---

## Exemplo prático

Relatórios mensais antigos podem ficar em Standard-IA se raramente consultados, mas ainda precisarem ser baixados rapidamente quando alguém solicitar.

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

* backups recentes;
* documentos antigos consultados ocasionalmente;
* arquivos de recuperação;
* dados acessados poucas vezes por mês;
* objetos que ainda precisam de acesso imediato quando solicitados.

**Trade-off**

O custo de armazenamento é menor que [[Amazon S3|S3]] Standard, mas há cobrança por recuperação e requisitos mínimos de armazenamento.

Se o dado for acessado com frequência, a economia pode desaparecer.

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

Não use Standard-IA para dados temporários de vida curta ou objetos muito acessados.

[[Amazon S3|S3]] pode parecer uma pasta, mas internamente trabalha com objetos identificados por chaves.

---

## Relação com outras notas

- [[Amazon S3]]
- [[Amazon EBS]]
- [[Amazon EFS]]
