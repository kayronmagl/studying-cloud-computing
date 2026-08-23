Armazenamento em Bloco é um modelo em que dados são divididos em blocos endereçáveis.

Para o sistema operacional, esse armazenamento aparece como um disco. A aplicação pode formatar o volume, criar sistema de arquivos, instalar software, gravar banco de dados ou persistir arquivos locais.

---

## O que é

Armazenamento em Bloco deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via [[APIs|API]], pense em [[Amazon S3|S3]]. Se for filesystem compartilhado, pense em EFS ou FSx.

---

## Por que existe

Armazenamento em Bloco existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

O sistema operacional envia operações de leitura e escrita para blocos.

Essas operações são avaliadas por:

* [[IOPS]];
* [[Throughput de Armazenamento]];
* [[Latência de Armazenamento]];
* tamanho de I/O;
* fila de disco;
* padrão aleatório ou sequencial.

**Uso Correto**

Armazenamento em bloco é forte quando existe necessidade de disco persistente, baixa latência e controle pelo sistema operacional.

Ele não deve ser escolhido apenas porque “parece mais familiar”. Em nuvem, familiaridade nem sempre significa melhor custo, resiliência ou escala.

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

**Diferença para Objeto**

No [[Armazenamento de Objetos]], a aplicação acessa objetos por [[APIs|API]].

No armazenamento em bloco, a aplicação acessa um dispositivo parecido com disco.

Por isso, [[Amazon EBS]] é adequado para instâncias [[Amazon EC2]], enquanto [[Amazon S3]] é adequado para arquivos distribuídos, data lakes e objetos.

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

- [[IOPS]]
- [[Throughput de Armazenamento]]
- [[Latência de Armazenamento]]
- [[Amazon EBS]]
- [[Amazon S3]]
- [[Amazon EFS]]
- [[Armazenamento de Objetos]]
- [[Amazon EC2]]
