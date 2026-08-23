Bancos de Dados da AWS formam uma família de serviços gerenciados para persistência, consulta, análise, cache e relacionamento de dados.

A AWS não oferece apenas um banco universal. Ela segue a lógica de [[Bancos de Dados Purpose-Built]], na qual cada banco é otimizado para um padrão de acesso.

Bancos de Dados da AWS deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Bancos de Dados da AWS deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

Bancos de Dados da AWS existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**Famílias Principais**

* [[Amazon RDS]] e [[Amazon Aurora]] para bancos relacionais.
* [[Amazon DynamoDB]] para NoSQL.
* [[Amazon ElastiCache]] e [[Amazon MemoryDB]] para memória.
* [[Amazon Redshift]] para data warehouse.
* [[Amazon DocumentDB]] para documentos.
* [[Amazon Neptune]] para grafos.
* [[Amazon Timestream]] para séries temporais.
* [[Amazon Keyspaces]] para Cassandra.
* [[Amazon OpenSearch Service]] para busca e análise textual.

**Banco não é Apenas Armazenamento**

Armazenamento guarda bytes.

Banco de dados oferece modelo de consulta, índices, transações, consistência, concorrência, recuperação e semântica de acesso.

---

## Exemplo prático

Uma aplicação de pedidos pode usar:

* [[Amazon RDS]] para transações;
* [[Amazon DynamoDB]] para acesso por chave em alta escala;
* [[Amazon ElastiCache]] para reduzir latência;
* [[Amazon Redshift]] para análise;
* [[Amazon S3]] como data lake.

Cada banco resolve um tipo de problema.

---

## Diferenças importantes

**Como Escolher**

A escolha começa pelo modelo de acesso:

* preciso consultar por relações?: relacional.
* preciso acessar por chave em altíssima escala?: [[Amazon DynamoDB|DynamoDB]].
* preciso analisar grandes volumes?: Redshift.
* preciso de cache rápido?: ElastiCache ou MemoryDB.
* preciso navegar relacionamentos?: Neptune.
* preciso consultar por tempo?: Timestream.

**Como Diferenciar**

* [[Amazon RDS|RDS]]/Aurora: relacional e transacional.
* [[Amazon DynamoDB|DynamoDB]]: NoSQL chave-valor/documento.
* ElastiCache: cache em memória.
* Redshift: data warehouse.
* Neptune: grafos.
* Timestream: séries temporais.

---

## Cuidados

A escolha do banco deve partir do padrão de acesso.

Perguntas importantes:

* preciso de transação?
* preciso de join?
* preciso de baixa latência por chave?
* preciso de analytics?
* preciso de relacionamento em grafo?

Escolher banco só pelo nome do serviço costuma gerar arquitetura ruim.

NoSQL não é “sem modelagem”. Em [[Amazon DynamoDB|DynamoDB]], modelagem é orientada pelas consultas.

---

## Relação com outras notas

**Conceitos que completam o assunto**

A visão fica mais completa ao separar [[Bancos de Dados NoSQL]], [[Bancos de Dados de Grafos]], [[Bancos de Dados de Séries Temporais]], [[Bancos de Dados em Memória]] e [[Data Warehouses]]. Cada modelo atende padrões de dados e consultas diferentes.
