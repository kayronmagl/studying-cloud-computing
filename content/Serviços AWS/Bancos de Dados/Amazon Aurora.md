Amazon Aurora é um banco relacional gerenciado da AWS compatível com MySQL e PostgreSQL.

Ele faz parte da família relacional, mas usa uma arquitetura de armazenamento distribuído própria da AWS, separando parte do mecanismo de computação e armazenamento.

Amazon Aurora deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Amazon Aurora deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

Aurora foi criado para oferecer performance, disponibilidade e operação gerenciada além do banco relacional tradicional.

Ele mantém compatibilidade com ecossistemas MySQL/PostgreSQL, mas oferece recursos nativos de nuvem.

---

## Como funciona

**Características**

* compatibilidade com MySQL ou PostgreSQL;
* replicação distribuída;
* alta disponibilidade;
* read replicas;
* backups automáticos;
* integração com [[Amazon RDS]];
* opções serverless em determinados modos.

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

**Quando Usar**

Use quando precisa de banco relacional gerenciado com forte disponibilidade, escala de leitura e integração profunda com AWS.

**Como Diferenciar**

* [[Amazon RDS|RDS]]/Aurora: relacional e transacional.
* [[Amazon DynamoDB|DynamoDB]]: NoSQL chave-valor/documento.
* ElastiCache: cache em memória.
* Redshift: data warehouse.
* Neptune: grafos.
* Timestream: séries temporais.

---

## Cuidados

Aurora não elimina necessidade de modelagem, índices e boas queries.

Um banco gerenciado ainda pode ser mal projetado.

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

- [[Amazon RDS]]
- [[Amazon DynamoDB]]
- [[Amazon ElastiCache]]
- [[Amazon Redshift]]
- [[Amazon S3]]
