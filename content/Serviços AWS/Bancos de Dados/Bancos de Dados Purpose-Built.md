Bancos de Dados Purpose-Built são bancos criados para finalidades específicas.

A ideia é que diferentes modelos de dados exigem motores diferentes. Um banco relacional não é sempre a melhor escolha para chave-valor em escala massiva. Um banco de grafos não substitui um data warehouse. Um cache em memória não substitui armazenamento durável.

Bancos de Dados Purpose-Built deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Bancos de Dados Purpose-Built deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

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

## Como funciona

**Exemplos AWS**

* [[Amazon RDS]] para relacional.
* [[Amazon DynamoDB]] para chave-valor e documento.
* [[Amazon Redshift]] para analytics.
* [[Amazon Neptune]] para grafos.
* [[Amazon Timestream]] para séries temporais.
* [[Amazon OpenSearch Service]] para busca.
* [[Amazon ElastiCache]] para cache.

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

Purpose-built não significa usar muitos bancos sem critério.

Cada novo banco aumenta operação, integração, consistência, custo e complexidade mental.

A decisão precisa ser justificada por padrão de acesso real.

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
- [[Amazon Redshift]]
- [[Amazon Neptune]]
- [[Amazon Timestream]]
- [[Amazon OpenSearch Service]]
- [[Amazon ElastiCache]]
- [[Amazon S3]]
