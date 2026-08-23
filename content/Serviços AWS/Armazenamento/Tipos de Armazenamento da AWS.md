Os Tipos de Armazenamento da AWS representam modelos diferentes de persistência, cada um desenhado para um padrão de uso específico.

A AWS não trata armazenamento como uma categoria única. Um disco de sistema operacional, um [[Buckets S3|bucket]] de imagens, um filesystem compartilhado, um backup de longo prazo e uma tabela de banco possuem necessidades diferentes de latência, consistência, durabilidade, custo e forma de acesso.

---

## O que é

Tipos de Armazenamento da AWS deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via [[APIs|API]], pense em [[Amazon S3|S3]]. Se for filesystem compartilhado, pense em EFS ou FSx.

---

## Por que existe

Tipos de Armazenamento da AWS existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**Modelos Principais**

Os modelos centrais são:

* [[Armazenamento em Bloco]];
* [[Armazenamento de Objetos]];
* [[Armazenamento de Arquivos]];
* armazenamento de banco de dados;
* armazenamento arquival;
* cache em memória.

Na prática, eles aparecem em serviços como [[Amazon EBS]], [[Amazon S3]], [[Amazon EFS]], [[Amazon FSx]], [[Amazon RDS]], [[Amazon DynamoDB]], [[Amazon Redshift]] e [[Amazon ElastiCache]].

**Decisão Arquitetural**

Uma pergunta correta não é “qual serviço é melhor?”.

* qual é o padrão de acesso dos dados?

Depois disso, avaliam-se latência, throughput, IOPS, consistência, custo, durabilidade, resiliência e integração com a aplicação.

Um erro comum é usar [[Amazon EC2]] com disco local para dados que deveriam estar no [[Amazon S3]], ou usar [[Amazon S3|S3]] como se fosse disco de baixa latência. Cada modelo tem uma semântica própria.

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

**Comparação Prática**

A escolha do tipo de armazenamento depende de como a aplicação acessa os dados.

* precisa de disco anexado a uma instância?: armazenamento em bloco.
* precisa guardar arquivos como objetos via [[APIs|API]]?: armazenamento de objetos.
* precisa de filesystem compartilhado por várias máquinas?: armazenamento de arquivos.
* precisa de persistência com consultas e transações?: banco de dados.

Essa separação evita confundir [[Amazon S3|S3]] com disco, EBS com filesystem compartilhado e EFS com banco de dados.

**Critério de Escolha**

Pergunte:

* a aplicação precisa de disco?
* precisa de [[APIs|API]] de objeto?
* precisa compartilhar arquivos entre máquinas?
* precisa arquivar por anos?
* precisa recuperar imediatamente?

Responder essas perguntas evita usar [[Amazon S3|S3]] como se fosse disco, EBS como se fosse compartilhado, ou EFS como se fosse banco.

**Como Diferenciar**

* bloco é diferente de objeto;
* objeto é diferente de arquivo compartilhado;
* classe de armazenamento altera custo e recuperação;
* lifecycle automatiza economia;
* versionamento e backup ajudam recuperação.

---

## Cuidados

Não escolha armazenamento só pelo nome do serviço. Escolha pelo padrão de acesso.

---

## Relação com outras notas

- [[Armazenamento em Bloco]]
- [[Armazenamento de Objetos]]
- [[Armazenamento de Arquivos]]
- [[Amazon EBS]]
- [[Amazon S3]]
- [[Amazon EFS]]
- [[Amazon FSx]]
- [[Amazon RDS]]
- [[Amazon DynamoDB]]
- [[Amazon Redshift]]
