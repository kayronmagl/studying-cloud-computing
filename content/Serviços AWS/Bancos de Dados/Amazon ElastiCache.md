Amazon ElastiCache é o serviço gerenciado de cache em memória da AWS, com suporte a Redis OSS e Memcached.

Ele é usado para reduzir latência e aliviar bancos de dados.

Amazon ElastiCache deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Amazon ElastiCache deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

Amazon ElastiCache existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**Papel**

Cache armazena dados frequentemente acessados em memória.

Isso reduz consultas repetidas a bancos como [[Amazon RDS]], [[Amazon Aurora]] ou [[Amazon DynamoDB]].

**Usos**

* cache de consultas;
* sessões;
* rankings;
* rate limiting;
* dados temporários;
* redução de latência;
* aliviar banco primário.

**Cache-aside**

Um padrão comum é cache-aside:

* aplicação consulta cache: se encontrou, retorna.
* se não encontrou: consulta banco.
* salva no cache: retorna.

**Velocidade e cache**

[[Bancos de Dados em Memória]] explicam por que serviços como ElastiCache reduzem latência em leituras frequentes.

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

Cache não deve ser a única fonte da verdade para dados críticos, salvo desenho específico.

É preciso lidar com expiração, invalidação, consistência e fallback.

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
- [[Amazon Aurora]]
- [[Amazon DynamoDB]]
- [[Bancos de Dados em Memória]]
- [[Amazon Redshift]]
- [[Amazon S3]]
