Os Tipos de Armazenamento da AWS representam modelos diferentes de persistência, cada um desenhado para um padrão de uso específico.

A AWS não trata armazenamento como uma categoria única. Um disco de sistema operacional, um bucket de imagens, um filesystem compartilhado, um backup de longo prazo e uma tabela de banco possuem necessidades diferentes de latência, consistência, durabilidade, custo e forma de acesso.

## Modelos Principais

Os modelos centrais são:

* [[Armazenamento em Bloco]];
* [[Armazenamento de Objetos]];
* [[Armazenamento de Arquivos]];
* armazenamento de banco de dados;
* armazenamento arquival;
* cache em memória.

Na prática, eles aparecem em serviços como [[Amazon EBS]], [[Amazon S3]], [[Amazon EFS]], [[Amazon FSx]], [[Amazon RDS]], [[Amazon DynamoDB]], [[Amazon Redshift]] e [[Amazon ElastiCache]].

---

## Decisão Arquitetural

Uma pergunta correta não é “qual serviço é melhor?”.


* qual é o padrão de acesso dos dados?


Depois disso, avaliam-se latência, throughput, IOPS, consistência, custo, durabilidade, resiliência e integração com a aplicação.

Um erro comum é usar [[Amazon EC2]] com disco local para dados que deveriam estar no [[Amazon S3]], ou usar S3 como se fosse disco de baixa latência. Cada modelo tem uma semântica própria.

---

## Comparação Prática

A escolha do tipo de armazenamento depende de como a aplicação acessa os dados.


* precisa de disco anexado a uma instância?: armazenamento em bloco.
* precisa guardar arquivos como objetos via API?: armazenamento de objetos.
* precisa de filesystem compartilhado por várias máquinas?: armazenamento de arquivos.
* precisa de persistência com consultas e transações?: banco de dados.


Essa separação evita confundir S3 com disco, EBS com filesystem compartilhado e EFS com banco de dados.

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
