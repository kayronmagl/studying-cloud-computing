Amazon RDS significa Amazon Relational Database Service.

É o serviço da AWS para criar, operar e escalar bancos relacionais gerenciados.

Ele suporta motores como PostgreSQL, MySQL, MariaDB, Oracle, SQL Server e Db2.

---

## Visão geral

Amazon RDS deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que o RDS Gerencia

RDS reduz trabalho operacional em:

* provisionamento;
* backups;
* snapshots;
* patching;
* monitoramento;
* failover;
* replicação;
* armazenamento;
* manutenção.

O cliente continua responsável por schema, queries, índices, permissões, segurança de acesso, modelagem e custo.

---

## DB Instance

A unidade principal é a [[DB Instance]].

Ela possui motor, classe, armazenamento, endpoint, porta, parâmetros, backups, rede e configuração de segurança.

---

## Multi-AZ

[[Multi-AZ]] aumenta disponibilidade.

Em configurações tradicionais, há uma instância standby em outra [[Availability Zones (AZ)|Availability Zone]] para failover.

---

## Read Replicas

[[Read Replicas]] ajudam a escalar leitura.

Elas não substituem Multi-AZ. Multi-AZ é disponibilidade. Read Replica é escala de leitura.

---

## Quando Usar

Use RDS quando a aplicação precisa de SQL, relações, transações, integridade e compatibilidade com motores tradicionais.

---

## Exemplo Prático

Uma aplicação de pedidos pode usar:

* [[Amazon RDS]] para transações;
* [[Amazon DynamoDB]] para acesso por chave em alta escala;
* [[Amazon ElastiCache]] para reduzir latência;
* [[Amazon Redshift]] para análise;
* [[Amazon S3]] como data lake.

Cada banco resolve um tipo de problema.

---

## Cuidados importantes

A escolha do banco deve partir do padrão de acesso.

Perguntas importantes:


* preciso de transação?
* preciso de join?
* preciso de baixa latência por chave?
* preciso de analytics?
* preciso de relacionamento em grafo?


Escolher banco só pelo nome do serviço costuma gerar arquitetura ruim.

## Explicação principal

Amazon RDS é o serviço gerenciado de bancos relacionais da AWS.

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
