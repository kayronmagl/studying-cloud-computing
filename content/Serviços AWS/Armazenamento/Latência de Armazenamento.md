Latência de Armazenamento é o tempo entre uma solicitação de leitura ou escrita e a resposta do sistema de armazenamento.

Ela afeta aplicações interativas, bancos transacionais e qualquer sistema sensível a tempo de resposta.

## Latência vs Throughput

Baixa latência significa resposta rápida por operação.

Alto throughput significa grande volume transferido por tempo.

São métricas diferentes.

---

## Onde Importa

Latência é crítica em [[Amazon RDS]], bancos autogerenciados em [[Amazon EC2]], caches, autenticação, operações transacionais e aplicações com usuários esperando resposta.

---

## Relação com S3

[[Amazon S3]] é excelente para objetos, mas não deve ser tratado como disco local de baixa latência.

Acesso por API a objetos é diferente de I/O de bloco.

---

## Relação com EBS

[[Amazon EBS]] é mais adequado quando a aplicação precisa de comportamento de disco com baixa latência.

Volumes de IOPS provisionado existem exatamente para workloads sensíveis.

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
