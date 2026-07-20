Amazon EBS significa Amazon Elastic Block Store.

É o serviço de [[Armazenamento em Bloco]] persistente da AWS para instâncias [[Amazon EC2]]. Um volume EBS funciona como um disco virtual que pode ser anexado a uma instância, formatado pelo sistema operacional e usado por aplicações.

## Volumes

[[Volumes do Amazon EBS]] são criados dentro de uma [[Availability Zones (AZ)]]. Normalmente, a instância EC2 que usa o volume precisa estar na mesma zona.

Isso conecta EBS diretamente ao desenho de disponibilidade. Se uma aplicação precisa sobreviver à falha de uma zona, não basta ter um volume EBS. É preciso pensar em replicação, snapshots, backups, multi-AZ ou outro serviço gerenciado.

---

## Tipos de Volume

[[Tipos de Volume do Amazon EBS]] incluem SSDs de propósito geral, SSDs com IOPS provisionado e HDDs otimizados para throughput ou baixo custo.

A escolha deve partir do padrão de I/O:


* uso geral: gp3.
* muitas operações críticas: io2.
* grandes leituras sequenciais: st1.
* dados frios em bloco: sc1.


---

## Snapshots

[[Snapshots do Amazon EBS]] são backups incrementais de volumes.

Eles permitem restaurar volumes, copiar dados entre regiões, criar estratégias de recuperação e reduzir risco operacional.

Para bancos autogerenciados, consistência de snapshot exige cuidado com buffers, escrita em andamento e mecanismos do banco.

---

## Exemplo

Uma empresa roda PostgreSQL manualmente em EC2.

Ela pode usar `io2` para IOPS previsível, snapshots automatizados, criptografia, alarmes no [[Amazon CloudWatch]] e replicação no próprio banco.

Nesse caso, o EBS é parte crítica da camada de dados.

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
