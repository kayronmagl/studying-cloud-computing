Throughput de Armazenamento é a quantidade de dados transferidos por unidade de tempo.

Ele costuma ser medido em MiB/s, MB/s ou GB/s.

## Diferença para IOPS

[[IOPS]] mede operações.

Throughput mede volume.

Um workload pode ter poucas operações enormes ou muitas operações pequenas. Cada caso pressiona o armazenamento de forma diferente.

---

## Onde Importa

Throughput é importante em backups, logs, big data, processamento sequencial, streaming, transferência de arquivos grandes e data warehouses.

---

## Relação com AWS

Em [[Amazon EBS]], volumes como `st1` favorecem throughput.

Em [[Amazon S3]], throughput depende do paralelismo e do padrão de requisições.

Em [[Amazon EFS]], throughput depende de modos como Elastic, Provisioned e Bursting.

---

## Interpretação

Throughput deve ser analisado junto com latência, IOPS e custo.

Alta vazão não significa automaticamente bom desempenho para banco transacional.

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

---

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
