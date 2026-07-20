Amazon EFS significa Amazon Elastic File System.

É o serviço de [[Armazenamento de Arquivos]] elástico e compartilhado da AWS para workloads Linux. Ele permite que múltiplas instâncias, containers ou funções acessem o mesmo filesystem.

## Papel Técnico

EFS é usado quando vários clientes precisam montar e compartilhar arquivos.

Exemplos:

* servidores web com conteúdo comum;
* aplicações legadas;
* processamento paralelo;
* containers;
* funções [[AWS Lambda]] com dados compartilhados;
* ferramentas que esperam NFS.

---

## Mount Targets

[[Mount Targets do Amazon EFS]] são endpoints criados dentro de sub-redes da [[Amazon VPC]] para permitir que clientes montem o filesystem.

Normalmente, cria-se mount target em cada [[Availability Zones (AZ)]] usada pela aplicação.

---

## Performance e Throughput

[[Modos de Performance do Amazon EFS]] e [[Modos de Throughput do Amazon EFS]] definem como o filesystem responde a latência e volume de dados.

---

## Classes

[[Classes de Armazenamento do Amazon EFS]] ajudam a reduzir custo movendo arquivos conforme acesso.

---

## Diferença para EBS

[[Amazon EBS]] é disco de bloco para EC2.

EFS é filesystem compartilhado.

Se uma aplicação precisa de múltiplos servidores lendo e escrevendo no mesmo diretório, EFS pode ser mais adequado que EBS.

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

---

## Pontos que Costumam Gerar Confusão

Quando o cenário envolve armazenamento de arquivos compartilhado, simples e escalável para uso com servidores locais e instâncias EC2 Linux, a resposta é [[Amazon EFS]].

---

## Como entender

EFS é filesystem compartilhado.

Várias instâncias podem montar o mesmo sistema de arquivos.

---

## Comparação

* [[Amazon EBS|EBS]]: volume em bloco para uma instância.
* EFS: arquivo compartilhado para Linux.
* [[Amazon S3|S3]]: objetos em bucket.
* S3 Glacier: arquivamento.
