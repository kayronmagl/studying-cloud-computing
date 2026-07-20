Bancos de Dados NoSQL são bancos não relacionais criados para modelos de dados e escalas que nem sempre se encaixam bem no modelo tabular relacional.

Eles podem ser chave-valor, documento, colunas largas, grafos ou séries temporais.

---

## Visão geral

Bancos de Dados NoSQL deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Por que Existem

Aplicações modernas podem precisar de:

* esquema flexível;
* baixa latência;
* distribuição horizontal;
* alto volume de escrita;
* acesso por chave;
* escalabilidade global;
* dados sem estrutura tabular fixa.

---

## AWS

Na AWS, exemplos incluem:

* [[Amazon DynamoDB]];
* [[Amazon DocumentDB]];
* [[Amazon Keyspaces]];
* [[Amazon Neptune]];
* [[Amazon Timestream]].

---

## Diferença para Relacional

[[Bancos de Dados Relacionais]] são fortes em transações, joins e integridade estruturada.

NoSQL é forte quando o padrão de acesso favorece escala, flexibilidade ou modelo específico.

---

## Cuidado

NoSQL não significa “sem modelagem”.

Em muitos casos, a modelagem precisa ser ainda mais orientada às consultas reais da aplicação.

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
