Armazenamento de Arquivos é um modelo que fornece um sistema de arquivos compartilhado, com diretórios, nomes de arquivos e semântica familiar a sistemas operacionais.

Na AWS, os principais serviços são [[Amazon EFS]] e [[Amazon FSx]].

## Diferença para Bloco e Objeto

[[Armazenamento em Bloco]] oferece discos.

[[Armazenamento de Objetos]] oferece objetos por API.

Armazenamento de arquivos oferece filesystem compartilhado.

---

## Quando Usar

Use quando múltiplas instâncias precisam acessar os mesmos arquivos, aplicações legadas esperam filesystem, containers compartilham diretórios, funções Lambda precisam de arquivos comuns ou processamento paralelo usa diretórios compartilhados.

---

## Cuidados importantes

Filesystem compartilhado pode virar gargalo se usado como banco de dados improvisado.

Também exige atenção a permissões, throughput, latência e padrão de acesso.

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
