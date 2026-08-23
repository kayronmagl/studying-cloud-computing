Armazenamento de Arquivos é um modelo que fornece um sistema de arquivos compartilhado, com diretórios, nomes de arquivos e semântica familiar a sistemas operacionais.

Na AWS, os principais serviços são [[Amazon EFS]] e [[Amazon FSx]].

---

## O que é

Armazenamento de Arquivos deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via [[APIs|API]], pense em [[Amazon S3|S3]]. Se for filesystem compartilhado, pense em EFS ou FSx.

---

## Por que existe

Armazenamento de Arquivos existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

O funcionamento depende do tipo de dado, padrão de acesso, necessidade de durabilidade, performance, retenção e recuperação. Ao estudar Armazenamento de Arquivos, conecte capacidade, acesso, proteção, ciclo de vida e custo.

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

**Diferença para Bloco e Objeto**

[[Armazenamento em Bloco]] oferece discos.

[[Armazenamento de Objetos]] oferece objetos por [[APIs|API]].

Armazenamento de arquivos oferece filesystem compartilhado.

**Quando Usar**

Use quando múltiplas instâncias precisam acessar os mesmos arquivos, aplicações legadas esperam filesystem, containers compartilham diretórios, funções [[AWS Lambda|Lambda]] precisam de arquivos comuns ou processamento paralelo usa diretórios compartilhados.

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

Filesystem compartilhado pode virar gargalo se usado como banco de dados improvisado.

Também exige atenção a permissões, throughput, latência e padrão de acesso.

Não escolha armazenamento só pelo nome do serviço. Escolha pelo padrão de acesso.

---

## Relação com outras notas

- [[Amazon EFS]]
- [[Amazon FSx]]
- [[Amazon EBS]]
- [[Amazon S3]]
- [[Armazenamento em Bloco]]
- [[Armazenamento de Objetos]]
