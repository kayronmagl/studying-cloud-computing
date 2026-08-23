Latência de Armazenamento é o tempo entre uma solicitação de leitura ou escrita e a resposta do sistema de armazenamento.

Ela afeta aplicações interativas, bancos transacionais e qualquer sistema sensível a tempo de resposta.

---

## O que é

Latência de Armazenamento deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via [[APIs|API]], pense em [[Amazon S3|S3]]. Se for filesystem compartilhado, pense em EFS ou FSx.

---

## Por que existe

Latência de Armazenamento existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**Latência vs Throughput**

Baixa latência significa resposta rápida por operação.

Alto throughput significa grande volume transferido por tempo.

São métricas diferentes.

**Onde Importa**

Latência é crítica em [[Amazon RDS]], bancos autogerenciados em [[Amazon EC2]], caches, autenticação, operações transacionais e aplicações com usuários esperando resposta.

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

**Relação com [[Amazon S3|S3]]**

[[Amazon S3]] é excelente para objetos, mas não deve ser tratado como disco local de baixa latência.

Acesso por [[APIs|API]] a objetos é diferente de I/O de bloco.

**Relação com EBS**

[[Amazon EBS]] é mais adequado quando a aplicação precisa de comportamento de disco com baixa latência.

Volumes de IOPS provisionado existem exatamente para workloads sensíveis.
