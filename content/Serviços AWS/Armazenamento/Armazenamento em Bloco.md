Armazenamento em Bloco é um modelo em que dados são divididos em blocos endereçáveis.

Para o sistema operacional, esse armazenamento aparece como um disco. A aplicação pode formatar o volume, criar sistema de arquivos, instalar software, gravar banco de dados ou persistir arquivos locais.

## Como Funciona

O sistema operacional envia operações de leitura e escrita para blocos.

Essas operações são avaliadas por:

* [[IOPS]];
* [[Throughput de Armazenamento]];
* [[Latência de Armazenamento]];
* tamanho de I/O;
* fila de disco;
* padrão aleatório ou sequencial.

---

## Diferença para Objeto

No [[Armazenamento de Objetos]], a aplicação acessa objetos por API.

No armazenamento em bloco, a aplicação acessa um dispositivo parecido com disco.

Por isso, [[Amazon EBS]] é adequado para instâncias [[Amazon EC2]], enquanto [[Amazon S3]] é adequado para arquivos distribuídos, data lakes e objetos.

---

## Uso Correto

Armazenamento em bloco é forte quando existe necessidade de disco persistente, baixa latência e controle pelo sistema operacional.

Ele não deve ser escolhido apenas porque “parece mais familiar”. Em nuvem, familiaridade nem sempre significa melhor custo, resiliência ou escala.

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
