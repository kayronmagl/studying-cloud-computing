Amazon Redshift é o serviço de data warehouse da AWS.

Ele é usado para análise de grandes volumes de dados, consultas analíticas e workloads de BI.

Amazon Redshift deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Amazon Redshift deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

Amazon Redshift existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**Uso**

* relatórios;
* dashboards;
* análise histórica;
* agregações;
* consultas sobre grandes volumes;
* integração com data lakes.

**OLAP**

[[Amazon Redshift]] é voltado a OLAP, ou processamento analítico online.

Ele responde perguntas como:

* quanto vendemos por região?
* qual produto cresceu mais?
* qual foi a média mensal?
* quais usuários têm maior retenção?

Essas consultas varrem grandes volumes e fazem agregações.

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

**Diferença para [[Amazon RDS|RDS]]**

[[Amazon RDS]] é voltado a transações operacionais.

Redshift é voltado a análise.

* [[Amazon RDS|RDS]]: OLTP.
* Redshift: OLAP.

**Como Diferenciar**

* [[Amazon RDS|RDS]]/Aurora: relacional e transacional.
* [[Amazon DynamoDB|DynamoDB]]: NoSQL chave-valor/documento.
* ElastiCache: cache em memória.
* Redshift: data warehouse.
* Neptune: grafos.
* Timestream: séries temporais.

---

## Cuidados

Não use Redshift como banco transacional principal.

Ele é otimizado para análise, não para pequenas transações concorrentes de aplicação.

Não use Redshift como banco da aplicação transacional. Para pedidos, usuários e pagamentos em tempo real, [[Amazon RDS]], [[Amazon Aurora]] ou [[Amazon DynamoDB]] costumam fazer mais sentido.

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

**Relação com [[Amazon S3|S3]]**

Redshift frequentemente se conecta a dados armazenados no [[Amazon S3]], formando arquiteturas de data lake e analytics.

[[Amazon S3|S3]] guarda dados brutos ou processados. Redshift consulta, agrega e serve relatórios.
