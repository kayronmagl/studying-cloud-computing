Amazon MemoryDB é um banco em memória compatível com Redis, projetado para durabilidade e baixa latência.

Ele se diferencia de cache puro porque pode atuar como banco primário em memória para determinados workloads.


Amazon MemoryDB deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Diferença para ElastiCache

[[Amazon ElastiCache]] é normalmente usado como cache.

MemoryDB busca oferecer durabilidade maior para dados em memória.

---

## Usos

* aplicações de baixa latência;
* estado de sessão durável;
* contadores;
* placares;
* workloads compatíveis com Redis que exigem persistência.

---

## Cuidado

Memória é cara.

Use quando latência e modelo de acesso justificam o custo.

---

## Relação com ElastiCache

[[Amazon ElastiCache]] é usado principalmente como cache.

[[Amazon MemoryDB]] é mais adequado quando a aplicação quer compatibilidade com Redis, baixa latência e durabilidade maior para atuar como fonte primária de dados em memória.

---

## Decisão Arquitetural

Use MemoryDB quando a perda do dado em memória não é aceitável e quando a latência extremamente baixa justifica custo.

Se os dados já existem em outro banco e a intenção é apenas acelerar leitura, ElastiCache costuma ser a escolha mental mais simples.

---

## Cuidado na prática

Memória é uma camada cara. A modelagem precisa controlar tamanho dos dados, política de expiração, replicação, persistência e impacto financeiro.

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
