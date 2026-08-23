Volumes do Amazon EBS são unidades persistentes de [[Armazenamento em Bloco]] usadas por instâncias [[Amazon EC2]].

Eles funcionam como discos virtuais. Depois de anexados, podem ser particionados, formatados, montados e usados pelo sistema operacional.

---

## O que é

Volumes do Amazon EBS deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via [[APIs|API]], pense em [[Amazon S3|S3]]. Se for filesystem compartilhado, pense em EFS ou FSx.

---

## Por que existe

Volumes do Amazon EBS existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**Ciclo de Vida**

Um volume pode ser criado, anexado, montado, usado, desanexado, redimensionado, copiado por snapshot e removido.

Esse ciclo pode ser independente da instância.

**Volume Raiz e Volume de Dados**

O volume raiz contém o sistema operacional.

Volumes de dados armazenam arquivos, logs, bancos ou dados persistentes.

Separar raiz e dados melhora manutenção e recuperação. Uma instância pode ser substituída sem destruir necessariamente os dados.

**Zona**

Volumes EBS são zonais.

Um volume pertence a uma [[Availability Zones (AZ)]]. Isso melhora baixa latência com a instância, mas exige planejamento para recuperação regional ou multi-AZ.

**Performance**

A performance depende de tipo de volume, tamanho, IOPS, throughput, instância [[Amazon EC2|EC2]], sistema de arquivos e padrão da aplicação.

Um volume rápido não corrige uma aplicação mal indexada, um banco sem tuning ou uma instância incapaz de entregar throughput suficiente.

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
- [[Amazon EC2]]
- [[Availability Zones (AZ)]]
- [[Amazon EBS]]
- [[Amazon S3]]
- [[Amazon EFS]]
