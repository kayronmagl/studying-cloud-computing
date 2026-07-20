Amazon Aurora é um banco relacional gerenciado da AWS compatível com MySQL e PostgreSQL.

Ele faz parte da família relacional, mas usa uma arquitetura de armazenamento distribuído própria da AWS, separando parte do mecanismo de computação e armazenamento.

---

## Visão geral

Amazon Aurora deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Por que Existe

Aurora foi criado para oferecer performance, disponibilidade e operação gerenciada além do banco relacional tradicional.

Ele mantém compatibilidade com ecossistemas MySQL/PostgreSQL, mas oferece recursos nativos de nuvem.

---

## Características

* compatibilidade com MySQL ou PostgreSQL;
* replicação distribuída;
* alta disponibilidade;
* read replicas;
* backups automáticos;
* integração com [[Amazon RDS]];
* opções serverless em determinados modos.

---

## Quando Usar

Use quando precisa de banco relacional gerenciado com forte disponibilidade, escala de leitura e integração profunda com AWS.

---

## Cuidado

Aurora não elimina necessidade de modelagem, índices e boas queries.

Um banco gerenciado ainda pode ser mal projetado.

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
