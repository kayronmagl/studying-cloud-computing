IOPS significa Input/Output Operations Per Second.

É a quantidade de operações de leitura e escrita que um sistema de armazenamento consegue executar por segundo.

---

## O que é

IOPS deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via [[APIs|API]], pense em [[Amazon S3|S3]]. Se for filesystem compartilhado, pense em EFS ou FSx.

---

## Por que existe

IOPS existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**IOPS vs Throughput**

[[IOPS]] mede quantidade de operações.

[[Throughput de Armazenamento]] mede volume de dados transferido.

* muitas leituras pequenas: IOPS.
* poucas leituras grandes: throughput.

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

**Quando Importa**

IOPS importa quando há muitas operações pequenas ou aleatórias.

Exemplos:

* bancos transacionais;
* sistemas com muitos índices;
* filas locais;
* workloads com muitos arquivos pequenos;
* operações de metadados.

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

**Erro Comum**

Aumentar apenas tamanho do volume esperando resolver qualquer lentidão.

O gargalo pode estar em IOPS, throughput, latência, instância, sistema de arquivos, índice do banco ou query mal escrita.

Não escolha armazenamento só pelo nome do serviço. Escolha pelo padrão de acesso.

---

## Relação com outras notas

**Relação com EBS**

Em [[Amazon EBS]], volumes como `io2` são escolhidos para IOPS provisionado.

Volumes como `st1` priorizam throughput sequencial.
