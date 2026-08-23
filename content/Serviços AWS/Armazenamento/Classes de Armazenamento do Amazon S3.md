Classes de Armazenamento do [[Amazon S3]] definem como objetos são armazenados em termos de custo, disponibilidade, frequência de acesso e tempo de recuperação.

Cada objeto no [[Amazon S3|S3]] possui uma classe de armazenamento. Se nenhuma classe for especificada, o padrão é [[S3 Standard]].

---

## O que é

Classes de Armazenamento do Amazon S3 deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

[[Amazon S3|S3]] trabalha com [[Buckets S3|buckets]] e objetos. Ele é acessado por [[APIs|API]] e é usado para arquivos, imagens, logs, backups, data lakes e conteúdo estático.

---

## Por que existe

Classes de Armazenamento do [[Amazon S3]] existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**Por que Existem**

Nem todo dado precisa do mesmo nível de acesso.

Um arquivo usado todos os dias precisa de acesso imediato. Um backup antigo pode aceitar restauração mais lenta. Um log regulatório pode ficar guardado por anos sem consulta frequente.

As classes permitem alinhar custo ao valor operacional do dado.

**Classes Principais**

* [[S3 Standard]];
* [[S3 Intelligent-Tiering]];
* [[S3 Standard-IA]];
* [[S3 One Zone-IA]];
* [[S3 Glacier Instant Retrieval]];
* [[S3 Glacier Flexible Retrieval]];
* [[S3 Glacier Deep Archive]].

**Lifecycle**

[[S3 Lifecycle]] automatiza transição entre classes.

Isso conecta arquitetura técnica com governança e custo.

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

**Critérios de Escolha**

Considere frequência de acesso, tempo de recuperação, custo de armazenamento, custo de recuperação, duração mínima, resiliência, conformidade e criticidade.

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

- [[S3 Standard]]
- [[Amazon S3]]
- [[S3 Intelligent-Tiering]]
- [[S3 Standard-IA]]
- [[S3 One Zone-IA]]
- [[S3 Glacier Instant Retrieval]]
- [[S3 Glacier Flexible Retrieval]]
- [[S3 Glacier Deep Archive]]
- [[S3 Lifecycle]]
- [[Amazon EBS]]
