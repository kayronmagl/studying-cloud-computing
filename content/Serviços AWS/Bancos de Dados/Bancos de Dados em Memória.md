Bancos de Dados em Memória mantêm dados principalmente em RAM para oferecer latência muito baixa.

Eles são usados quando acesso rápido é mais importante que custo por GB.

Bancos de Dados em Memória deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Bancos de Dados em Memória deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

Bancos de Dados em Memória existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**AWS**

Serviços relevantes:

* [[Amazon ElastiCache]];
* [[Amazon MemoryDB]].

**Cache vs Banco**

Cache acelera acesso a dados que existem em outro lugar.

Banco em memória pode ser a fonte primária, dependendo do serviço e configuração.

**Latência**

Bancos em memória reduzem latência porque acessam dados principalmente em RAM.

Isso é útil para sessões, rankings, tokens, contadores, cache de consultas e dados temporários de alto acesso.

**Cache vs Fonte Primária**

[[Amazon ElastiCache]] é geralmente usado como cache.

[[Amazon MemoryDB]] pode atuar como fonte primária Redis-compatible com durabilidade maior.

A diferença muda a responsabilidade da aplicação: perder cache pode ser aceitável; perder banco primário não.

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

**Como Diferenciar**

* [[Amazon RDS|RDS]]/Aurora: relacional e transacional.
* [[Amazon DynamoDB|DynamoDB]]: NoSQL chave-valor/documento.
* ElastiCache: cache em memória.
* Redshift: data warehouse.
* Neptune: grafos.
* Timestream: séries temporais.

---

## Cuidados

É preciso pensar em expiração, durabilidade, replicação, recuperação, custo e consistência.

Memória custa mais que armazenamento em disco ou objeto. Só faz sentido quando a redução de latência compensa custo e complexidade.

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

- [[Amazon ElastiCache]]
- [[Amazon MemoryDB]]
- [[Amazon RDS]]
- [[Amazon DynamoDB]]
- [[Amazon Redshift]]
- [[Amazon S3]]
