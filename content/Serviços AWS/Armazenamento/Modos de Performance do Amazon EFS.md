Modos de Performance do Amazon EFS definem o perfil de latência e escala operacional de um filesystem EFS.

---

## O que é

Modos de Performance do Amazon EFS deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via [[APIs|API]], pense em [[Amazon S3|S3]]. Se for filesystem compartilhado, pense em EFS ou FSx.

---

## Por que existe

Modos de Performance do Amazon EFS existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**General Purpose**

É adequado para a maioria dos workloads e prioriza menor latência por operação.

**Max I/O**

É voltado a workloads que exigem maior escala de operações paralelas, aceitando latência um pouco maior.

**Escolha Técnica**

A escolha do modo de performance deve partir do comportamento da aplicação.

Aplicações web e diretórios compartilhados comuns geralmente se beneficiam de menor latência.

Workloads massivos e paralelos podem precisar de maior escala de operações, aceitando latência maior.

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

**Escolha**

A escolha depende do equilíbrio entre latência e paralelismo.

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

Escolher modo avançado sem necessidade pode aumentar complexidade. Primeiro entenda o padrão de acesso.

Não escolha armazenamento só pelo nome do serviço. Escolha pelo padrão de acesso.

---

## Relação com outras notas

**Relação com Throughput**

Performance mode não é a mesma coisa que [[Modos de Throughput do Amazon EFS]].

Performance mode afeta o perfil operacional do filesystem. Throughput mode afeta a vazão disponível.
