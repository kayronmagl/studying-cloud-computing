Buckets [[Amazon S3|S3]] são contêineres lógicos para objetos no [[Amazon S3]]. Eles concentram configurações de região, acesso, criptografia, versionamento e ciclo de vida.

---

## O que é

Buckets S3 deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Um bucket [[Amazon S3|S3]] é o contêiner lógico onde os [[Objetos S3|objetos S3]] ficam armazenados. Para um iniciante, a comparação mais próxima é uma pasta principal, mas a comparação é limitada: bucket não é uma pasta comum de sistema operacional.

O bucket concentra configurações administrativas. É nele que entram região, política de acesso, bloqueio de acesso público, criptografia padrão, versionamento, lifecycle, logs e replicação.

[[Amazon S3|S3]] trabalha com buckets e objetos. Ele é acessado por [[APIs]], [[AWS SDKs]], [[AWS CLI]], console e integrações com outros serviços.

---

## Por que existe

Buckets [[Amazon S3|S3]] existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

Um bucket é criado em uma região da AWS. Dentro dele ficam objetos, e cada objeto tem uma chave, que é o nome lógico usado para localizar aquele dado.

Exemplo de chave:

* `imagens/produtos/camiseta-azul.png`

Essa chave parece caminho de pasta, mas no [[Amazon S3|S3]] ela é apenas texto usado para identificar o objeto.

O bucket também define regras que afetam todos ou muitos objetos dentro dele: criptografia padrão, bloqueio de acesso público, política de bucket, versionamento, replicação e lifecycle.

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

Bucket público sem necessidade é risco grave. Antes de expor dados, verifique bloqueio de acesso público, políticas, permissões [[AWS Identity and Access Management (IAM)|IAM]], criptografia e auditoria.

Também não trate bucket como disco de aplicação. [[Amazon S3|S3]] é acessado por [[APIs|API]]; ele não substitui um volume EBS anexado a uma instância nem um filesystem compartilhado como EFS.

---

## Relação com outras notas

- [[Amazon S3]]
- [[Objetos S3]]
- [[AWS SDKs]]
- [[AWS CLI]]
- [[APIs]]
- [[Amazon EBS]]
- [[Amazon EFS]]
