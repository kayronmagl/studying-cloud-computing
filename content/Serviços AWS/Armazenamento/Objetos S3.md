Objetos [[Amazon S3|S3]] são as unidades de dado armazenadas no [[Amazon S3]].

Um objeto não é apenas o arquivo. Ele inclui conteúdo, chave, metadados e propriedades de armazenamento.

---

## O que é

Objetos S3 deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

[[Amazon S3|S3]] trabalha com [[Buckets S3|buckets]] e objetos. Ele é acessado por [[APIs|API]] e é usado para arquivos, imagens, logs, backups, data lakes e conteúdo estático.

---

## Por que existe

Objetos [[Amazon S3|S3]] existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**Componentes**

Um objeto possui:

* chave;
* dados;
* metadados;
* ETag;
* classe de armazenamento;
* criptografia;
* versão opcional;
* tags opcionais.

**Chave**

A chave identifica o objeto dentro do [[Buckets S3|bucket]].

Exemplo:

* relatorios/2026/janeiro.pdf

Essa estrutura parece diretório, mas é uma chave textual com barras. [[Amazon S3|S3]] não é filesystem tradicional.

**Metadados**

Metadados descrevem o objeto.

Eles podem incluir tipo de conteúdo, tamanho, informações de cache, criptografia, tags e dados customizados.

---

## Exemplo prático

Uma aplicação pode salvar imagens originais como objetos [[Amazon S3|S3]], gerar miniaturas com [[AWS Lambda]] e distribuir o conteúdo por [[Amazon CloudFront]].

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

---

## Relação com outras notas

**Relação com [[APIs|APIs]]**

Objetos são enviados, lidos e removidos por [[APIs|APIs]].

Isso diferencia [[Amazon S3|S3]] de [[Amazon EBS]] e [[Amazon EFS]]. A aplicação precisa pensar em operações de objeto, não em blocos de disco ou diretórios montados.
