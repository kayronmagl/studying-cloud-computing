Kinesis Shards são unidades de capacidade dentro de um [[Amazon Kinesis Data Streams|Kinesis Data Stream]].

Um stream é composto por um ou mais shards.

Kinesis Shards aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## O que é

[[Amazon RDS]] é o serviço gerenciado de bancos relacionais da AWS.

Ele suporta motores como MySQL, PostgreSQL, MariaDB, Oracle, SQL Server e outros conforme disponibilidade.

---

## Por que existe

Kinesis Shards existe para desacoplar partes de uma aplicação, absorver variação de carga e permitir comunicação assíncrona ou orientada a eventos. Sem mensageria, componentes ficam mais dependentes do tempo de resposta uns dos outros.

---

## Como funciona

**Função**

Cada shard recebe registros e permite leitura por consumidores.

A quantidade de shards influencia throughput de escrita e leitura.

**Resharding**

Ajustar número de shards permite adaptar capacidade do stream.

**Partition Key**

Quando um produtor envia registro ao Kinesis, a partition key ajuda a determinar o shard de destino.

Isso distribui carga.

Se muitas mensagens usam a mesma chave, podem concentrar tráfego em um shard.

**Capacidade**

A capacidade de um stream depende da quantidade de shards ou do modo de capacidade configurado.

Se producers enviam mais dados do que os shards suportam, ocorrem limites e atrasos.

**Monitoramento**

É importante acompanhar métricas de throughput, throttling e atraso de consumidores no [[Amazon CloudWatch]].

**O que a AWS Gerencia**

* provisionamento;
* backups automáticos;
* patches do mecanismo em certos cenários;
* armazenamento;
* snapshots;
* Multi-AZ;
* monitoramento básico.

**O que o Cliente Ainda Gerencia**

* modelo de dados;
* queries;
* índices;
* usuários do banco;
* permissões;
* parâmetros;
* performance da aplicação.

---

## Exemplo prático

Uma [[APIs|API]] pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Diferenças importantes

Não confunda fila, tópico, evento e stream. Fila distribui mensagens para processamento, tópico publica para assinantes, evento descreve algo ocorrido e stream preserva sequência de registros para consumo contínuo.

---

## Cuidados

Poucos shards podem limitar throughput.

Shards demais podem aumentar custo e complexidade.

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

[[Amazon RDS|RDS]] gerencia o banco, mas não cria automaticamente uma boa modelagem. Query ruim continua sendo query ruim.

---

## Relação com outras notas

**Relação com Partições**

Shards em Kinesis lembram partições em sistemas de streaming.

Eles distribuem carga e ordenação por chave.

- [[Amazon Kinesis Data Streams]]
- [[Amazon RDS]]
- [[Amazon CloudWatch]]
- [[Amazon SQS]]
- [[Dead Letter Queue (DLQ)]]
- [[Amazon SNS]]
- [[Amazon EventBridge]]
