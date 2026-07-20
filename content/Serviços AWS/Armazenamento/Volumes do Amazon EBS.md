Volumes do Amazon EBS são unidades persistentes de [[Armazenamento em Bloco]] usadas por instâncias [[Amazon EC2]].

Eles funcionam como discos virtuais. Depois de anexados, podem ser particionados, formatados, montados e usados pelo sistema operacional.

## Ciclo de Vida

Um volume pode ser criado, anexado, montado, usado, desanexado, redimensionado, copiado por snapshot e removido.

Esse ciclo pode ser independente da instância.

---

## Volume Raiz e Volume de Dados

O volume raiz contém o sistema operacional.

Volumes de dados armazenam arquivos, logs, bancos ou dados persistentes.

Separar raiz e dados melhora manutenção e recuperação. Uma instância pode ser substituída sem destruir necessariamente os dados.

---

## Zona

Volumes EBS são zonais.

Um volume pertence a uma [[Availability Zones (AZ)]]. Isso melhora baixa latência com a instância, mas exige planejamento para recuperação regional ou multi-AZ.

---

## Performance

A performance depende de tipo de volume, tamanho, IOPS, throughput, instância EC2, sistema de arquivos e padrão da aplicação.

Um volume rápido não corrige uma aplicação mal indexada, um banco sem tuning ou uma instância incapaz de entregar throughput suficiente.

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
