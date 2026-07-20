Data Records são registros enviados para [[Amazon Kinesis Data Streams]].

Cada registro contém dados, partition key e metadados como sequence number.

---

## Visão geral

Data Records aparece quando sistemas precisam conversar sem ficarem grudados um no outro. Mensageria serve para desacoplar, absorver picos e lidar melhor com falhas.

Ao estudar, pense sempre em produtor, consumidor, mensagem, retry e DLQ.

---

## Papel

Data records são a unidade de informação do stream.

Exemplos:

* evento de clique;
* linha de log;
* medição de sensor;
* evento de compra;
* métrica de aplicação.

---

## Partition Key

A partition key ajuda a determinar em qual [[Kinesis Shards|shard]] o registro será colocado.

---

## Cuidado

Escolher mal a partition key pode causar hot shard, concentrando carga em uma parte do stream.

---

## Exemplo

Um registro pode representar:


* sensor_id: 10
* temperatura: 32.5
* timestamp: 2026-07-01T10:00:00Z


Esse registro é enviado por um producer para o stream.

---

## Relação com Processamento

Consumers leem data records para agregar, filtrar, enriquecer ou enviar para outros destinos.

Em analytics, cada registro pode ser uma pequena parte de um fluxo contínuo.

---

## Cuidado na prática

Data records muito grandes podem afetar throughput e custo.

Também é importante escolher corretamente a partition key para evitar concentração de carga em um único shard.

---

## Exemplo Prático

Uma API pode receber uma solicitação, publicar uma mensagem em [[Amazon SQS]] e responder rapidamente ao usuário. Workers processam a fila depois. Se falharem, mensagens podem ser repetidas ou enviadas para [[Dead Letter Queue (DLQ)]].

Em outro cenário, [[Amazon SNS]] distribui uma mensagem para vários consumidores, enquanto [[Amazon EventBridge]] roteia eventos por padrão.

---

## Cuidados importantes

Mensageria exige lidar com duplicidade, ordem, atraso, reprocessamento e observabilidade.

Não basta “colocar na fila”. O consumidor precisa ser idempotente, monitorado e preparado para falhas.

## Explicação principal

[[Amazon RDS]] é o serviço gerenciado de bancos relacionais da AWS.

Ele suporta motores como MySQL, PostgreSQL, MariaDB, Oracle, SQL Server e outros conforme disponibilidade.

## O que a AWS Gerencia

* provisionamento;
* backups automáticos;
* patches do mecanismo em certos cenários;
* armazenamento;
* snapshots;
* Multi-AZ;
* monitoramento básico.

## O que o Cliente Ainda Gerencia

* modelo de dados;
* queries;
* índices;
* usuários do banco;
* permissões;
* parâmetros;
* performance da aplicação.

## Cuidado importante

RDS gerencia o banco, mas não cria automaticamente uma boa modelagem. Query ruim continua sendo query ruim.
