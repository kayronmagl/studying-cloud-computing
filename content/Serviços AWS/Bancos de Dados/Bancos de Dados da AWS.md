Bancos de Dados da AWS formam uma família de serviços gerenciados para persistência, consulta, análise, cache e relacionamento de dados.

A AWS não oferece apenas um banco universal. Ela segue a lógica de [[Bancos de Dados Purpose-Built]], na qual cada banco é otimizado para um padrão de acesso.


Bancos de Dados da AWS deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Famílias Principais

* [[Amazon RDS]] e [[Amazon Aurora]] para bancos relacionais.
* [[Amazon DynamoDB]] para NoSQL.
* [[Amazon ElastiCache]] e [[Amazon MemoryDB]] para memória.
* [[Amazon Redshift]] para data warehouse.
* [[Amazon DocumentDB]] para documentos.
* [[Amazon Neptune]] para grafos.
* [[Amazon Timestream]] para séries temporais.
* [[Amazon Keyspaces]] para Cassandra.
* [[Amazon OpenSearch Service]] para busca e análise textual.

---

## Banco não é Apenas Armazenamento

Armazenamento guarda bytes.

Banco de dados oferece modelo de consulta, índices, transações, consistência, concorrência, recuperação e semântica de acesso.

---

## Como Escolher

A escolha começa pelo modelo de acesso:


* preciso consultar por relações?: relacional.
* preciso acessar por chave em altíssima escala?: DynamoDB.
* preciso analisar grandes volumes?: Redshift.
* preciso de cache rápido?: ElastiCache ou MemoryDB.
* preciso navegar relacionamentos?: Neptune.
* preciso consultar por tempo?: Timestream.


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

---

## Conceitos que completam o assunto

A visão fica mais completa ao separar [[Bancos de Dados NoSQL]], [[Bancos de Dados de Grafos]], [[Bancos de Dados de Séries Temporais]], [[Bancos de Dados em Memória]] e [[Data Warehouses]]. Cada modelo atende padrões de dados e consultas diferentes.
