Modos de Performance do Amazon EFS definem o perfil de latência e escala operacional de um filesystem EFS.

## General Purpose

É adequado para a maioria dos workloads e prioriza menor latência por operação.

---

## Max I/O

É voltado a workloads que exigem maior escala de operações paralelas, aceitando latência um pouco maior.

---

## Escolha

A escolha depende do equilíbrio entre latência e paralelismo.

---

## Escolha Técnica

A escolha do modo de performance deve partir do comportamento da aplicação.

Aplicações web e diretórios compartilhados comuns geralmente se beneficiam de menor latência.

Workloads massivos e paralelos podem precisar de maior escala de operações, aceitando latência maior.

---

## Relação com Throughput

Performance mode não é a mesma coisa que [[Modos de Throughput do Amazon EFS]].

Performance mode afeta o perfil operacional do filesystem. Throughput mode afeta a vazão disponível.

---

## Cuidado

Escolher modo avançado sem necessidade pode aumentar complexidade. Primeiro entenda o padrão de acesso.

---

## Exemplo Prático

Uma aplicação pode usar:

* [[Amazon EBS]] para disco de uma instância;
* [[Amazon S3]] para objetos e arquivos;
* [[Amazon EFS]] para filesystem compartilhado;
* classes de armazenamento para reduzir custo de dados antigos.

Cada escolha muda o comportamento da aplicação.

---

## Critério de Escolha

Pergunte:


* a aplicação precisa de disco?
* precisa de API de objeto?
* precisa compartilhar arquivos entre máquinas?
* precisa arquivar por anos?
* precisa recuperar imediatamente?


Responder essas perguntas evita usar S3 como se fosse disco, EBS como se fosse compartilhado, ou EFS como se fosse banco.

## Como entender isso

Este conceito pertence ao módulo de armazenamento na AWS.

## Ponto central

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via API, pense em S3. Se for filesystem compartilhado, pense em EFS ou FSx.

## Como Diferenciar

* bloco é diferente de objeto;
* objeto é diferente de arquivo compartilhado;
* classe de armazenamento altera custo e recuperação;
* lifecycle automatiza economia;
* versionamento e backup ajudam recuperação.

## Cuidado importante

Não escolha armazenamento só pelo nome do serviço. Escolha pelo padrão de acesso.
