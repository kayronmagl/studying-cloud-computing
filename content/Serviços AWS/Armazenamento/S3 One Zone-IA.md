[[Amazon S3|S3]] One Zone-IA é uma classe do [[Amazon S3]] para dados de acesso infrequente armazenados em uma única [[Availability Zones (AZ)|Availability Zone]].

Ela custa menos que classes multi-AZ, mas tem menor resiliência contra perda de zona.

---

## O que é

S3 One Zone-IA deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

[[Amazon S3|S3]] trabalha com [[Buckets S3|buckets]] e objetos. Ele é acessado por [[APIs|API]] e é usado para arquivos, imagens, logs, backups, data lakes e conteúdo estático.

---

## Por que existe

[[Amazon S3|S3]] One Zone-IA existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**Pergunta Decisiva**

* posso reconstruir esse dado se a zona falhar?

Se a resposta for não, One Zone-IA pode ser inadequado.

---

## Exemplo prático

Miniaturas de imagens podem ficar em One Zone-IA se a aplicação mantém os arquivos originais em [[Amazon S3|S3]] Standard e consegue gerar miniaturas novamente.

Uma aplicação pode usar:

* [[Amazon EBS]] para disco de uma instância;
* [[Amazon S3]] para objetos e arquivos;
* [[Amazon EFS]] para filesystem compartilhado;
* classes de armazenamento para reduzir custo de dados antigos.

Cada escolha muda o comportamento da aplicação.

---

## Diferenças importantes

**Quando Usar**

Use para dados que podem ser recriados:

* thumbnails;
* caches persistentes;
* dados derivados;
* cópias secundárias;
* arquivos temporários importantes, mas reconstruíveis.

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

Não use para única cópia de dados críticos, regulatórios ou irrecuperáveis.

[[Amazon S3|S3]] pode parecer uma pasta, mas internamente trabalha com objetos identificados por chaves.

---

## Relação com outras notas

- [[Amazon S3]]
- [[Availability Zones (AZ)]]
- [[Amazon EBS]]
- [[Amazon EFS]]
