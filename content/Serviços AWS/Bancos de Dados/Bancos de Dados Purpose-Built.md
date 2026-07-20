Bancos de Dados Purpose-Built são bancos criados para finalidades específicas.

A ideia é que diferentes modelos de dados exigem motores diferentes. Um banco relacional não é sempre a melhor escolha para chave-valor em escala massiva. Um banco de grafos não substitui um data warehouse. Um cache em memória não substitui armazenamento durável.

---

## Visão geral

Bancos de Dados Purpose-Built deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Por que Importa

Durante muito tempo, muitas aplicações tentavam resolver quase tudo com banco relacional.

Isso ainda funciona em muitos casos, mas sistemas modernos podem precisar de vários modelos:

* transações;
* busca textual;
* séries temporais;
* cache;
* grafos;
* documentos;
* analytics;
* chave-valor.

---

## Exemplos AWS

* [[Amazon RDS]] para relacional.
* [[Amazon DynamoDB]] para chave-valor e documento.
* [[Amazon Redshift]] para analytics.
* [[Amazon Neptune]] para grafos.
* [[Amazon Timestream]] para séries temporais.
* [[Amazon OpenSearch Service]] para busca.
* [[Amazon ElastiCache]] para cache.

---

## Cuidado

Purpose-built não significa usar muitos bancos sem critério.

Cada novo banco aumenta operação, integração, consistência, custo e complexidade mental.

A decisão precisa ser justificada por padrão de acesso real.

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
