IOPS significa Input/Output Operations Per Second.

É a quantidade de operações de leitura e escrita que um sistema de armazenamento consegue executar por segundo.

## Quando Importa

IOPS importa quando há muitas operações pequenas ou aleatórias.

Exemplos:

* bancos transacionais;
* sistemas com muitos índices;
* filas locais;
* workloads com muitos arquivos pequenos;
* operações de metadados.

---

## IOPS vs Throughput

[[IOPS]] mede quantidade de operações.

[[Throughput de Armazenamento]] mede volume de dados transferido.


* muitas leituras pequenas: IOPS.
* poucas leituras grandes: throughput.


---

## Relação com EBS

Em [[Amazon EBS]], volumes como `io2` são escolhidos para IOPS provisionado.

Volumes como `st1` priorizam throughput sequencial.

---

## Erro Comum

Aumentar apenas tamanho do volume esperando resolver qualquer lentidão.

O gargalo pode estar em IOPS, throughput, latência, instância, sistema de arquivos, índice do banco ou query mal escrita.

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
