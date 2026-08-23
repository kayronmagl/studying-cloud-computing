Tipos de Volume do Amazon EBS definem o perfil de custo e desempenho de um volume.

A AWS oferece volumes SSD e HDD, cada um adequado a padrões diferentes de acesso.

---

## O que é

Tipos de Volume do Amazon EBS deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via [[APIs|API]], pense em [[Amazon S3|S3]]. Se for filesystem compartilhado, pense em EFS ou FSx.

---

## Por que existe

Tipos de Volume do Amazon EBS existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**gp3 e gp2**

`gp3` e `gp2` são SSDs de propósito geral.

`gp3` é comum para workloads gerais porque permite configurar IOPS e throughput com mais flexibilidade.

Usos:

* volumes raiz;
* aplicações web;
* bancos pequenos e médios;
* ambientes de desenvolvimento;
* workloads gerais.

**io2 e io1**

`io2` e `io1` são SSDs com IOPS provisionado.

São usados quando a aplicação precisa de desempenho previsível e baixa latência.

Usos:

* bancos críticos;
* workloads transacionais;
* aplicações sensíveis a I/O;
* sistemas de missão crítica.

**st1**

`st1` é HDD otimizado para throughput.

É adequado para leitura e escrita sequencial de grande volume.

Usos:

* big data;
* logs;
* processamento sequencial;
* data warehouses autogerenciados.

**sc1**

`sc1` é HDD frio.

É usado quando custo é prioridade e o acesso é menos frequente.

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

**Como Escolher**

Uma pergunta principal é:

* meu gargalo é IOPS, throughput, latência ou custo?

Essa pergunta evita escolher volume apenas pelo tamanho.

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

- [[Amazon EBS]]
- [[Amazon S3]]
- [[Amazon EFS]]
