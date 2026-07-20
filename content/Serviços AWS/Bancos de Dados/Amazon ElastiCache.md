Amazon ElastiCache é o serviço gerenciado de cache em memória da AWS, com suporte a Redis OSS e Memcached.

Ele é usado para reduzir latência e aliviar bancos de dados.

---

## Visão geral

Amazon ElastiCache deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Papel

Cache armazena dados frequentemente acessados em memória.

Isso reduz consultas repetidas a bancos como [[Amazon RDS]], [[Amazon Aurora]] ou [[Amazon DynamoDB]].

---

## Usos

* cache de consultas;
* sessões;
* rankings;
* rate limiting;
* dados temporários;
* redução de latência;
* aliviar banco primário.

---

## Cache-aside

Um padrão comum é cache-aside:


* aplicação consulta cache: se encontrou, retorna.
* se não encontrou: consulta banco.
* salva no cache: retorna.


---

## Cuidado

Cache não deve ser a única fonte da verdade para dados críticos, salvo desenho específico.

É preciso lidar com expiração, invalidação, consistência e fallback.

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

---

## Velocidade e cache

[[Bancos de Dados em Memória]] explicam por que serviços como ElastiCache reduzem latência em leituras frequentes.
