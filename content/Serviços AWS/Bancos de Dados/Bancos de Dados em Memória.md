Bancos de Dados em Memória mantêm dados principalmente em RAM para oferecer latência muito baixa.

Eles são usados quando acesso rápido é mais importante que custo por GB.


Bancos de Dados em Memória deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## AWS

Serviços relevantes:

* [[Amazon ElastiCache]];
* [[Amazon MemoryDB]].

---

## Cache vs Banco

Cache acelera acesso a dados que existem em outro lugar.

Banco em memória pode ser a fonte primária, dependendo do serviço e configuração.

---

## Cuidados importantes

É preciso pensar em expiração, durabilidade, replicação, recuperação, custo e consistência.

---

## Latência

Bancos em memória reduzem latência porque acessam dados principalmente em RAM.

Isso é útil para sessões, rankings, tokens, contadores, cache de consultas e dados temporários de alto acesso.

---

## Cache vs Fonte Primária

[[Amazon ElastiCache]] é geralmente usado como cache.

[[Amazon MemoryDB]] pode atuar como fonte primária Redis-compatible com durabilidade maior.

A diferença muda a responsabilidade da aplicação: perder cache pode ser aceitável; perder banco primário não.

---

## Cuidado

Memória custa mais que armazenamento em disco ou objeto. Só faz sentido quando a redução de latência compensa custo e complexidade.

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

## Cuidado adicional

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
