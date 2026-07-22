Uma DB Instance é a unidade operacional básica do [[Amazon RDS]].

Ela representa um ambiente de banco gerenciado com motor, classe de instância, armazenamento, endpoint, porta, parâmetros, backups e configurações de rede.


DB Instance deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Componentes

Uma DB Instance possui:

* motor;
* classe;
* armazenamento;
* usuário mestre;
* endpoint;
* porta;
* subnet group;
* security group;
* backups;
* parâmetros;
* janela de manutenção.

---

## Relação com VPC

DB Instances normalmente ficam dentro de uma [[Amazon VPC]], muitas vezes em sub-redes privadas.

Isso impede exposição direta à internet e permite acesso apenas por aplicações autorizadas.

---

## Operação

O RDS gerencia parte da operação, como provisionamento, backups automáticos e manutenção do serviço.

O cliente ainda cuida de schema, índices, queries, usuários do banco, parâmetros e acesso de rede.

---

## Cuidado

DB Instance não é apenas “um banco”.

É um recurso gerenciado que participa da arquitetura de rede, segurança, backup, disponibilidade e custo.

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

---

## Como entender isso

Este conceito pertence ao módulo de bancos de dados na AWS.

## Ponto central

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

## Como Diferenciar

* RDS/Aurora: relacional e transacional.
* DynamoDB: NoSQL chave-valor/documento.
* ElastiCache: cache em memória.
* Redshift: data warehouse.
* Neptune: grafos.
* Timestream: séries temporais.

## Cuidado importante

NoSQL não é “sem modelagem”. Em DynamoDB, modelagem é orientada pelas consultas.
