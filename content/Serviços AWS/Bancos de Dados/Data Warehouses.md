Data Warehouses são bancos analíticos usados para consolidar e consultar grandes volumes de dados históricos.

Eles são otimizados para leitura, agregação e análise, não para transações pequenas de alta frequência.

Data Warehouses deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Data Warehouses deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

Data Warehouses existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**OLTP vs OLAP**

OLTP é processamento transacional.

OLAP é processamento analítico.

[[Amazon RDS]] atende melhor OLTP. [[Amazon Redshift]] atende melhor OLAP.

**Uso**

* BI;
* relatórios;
* métricas históricas;
* análise de vendas;
* auditoria;
* dados consolidados de múltiplas fontes.

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

**Diferença para Banco Operacional**

Um banco operacional atende a aplicação em tempo real.

Um data warehouse atende análise.

Exemplo:

* [[Amazon RDS]]: registrar pedido agora.
* [[Amazon Redshift]]: analisar vendas dos últimos 3 anos.

Misturar essas funções pode gerar lentidão e custo.

**Como Diferenciar**

* [[Amazon RDS|RDS]]/Aurora: relacional e transacional.
* [[Amazon DynamoDB|DynamoDB]]: NoSQL chave-valor/documento.
* ElastiCache: cache em memória.
* Redshift: data warehouse.
* Neptune: grafos.
* Timestream: séries temporais.

---

## Cuidados

Data warehouse mal modelado pode ficar caro e lento.

É preciso pensar em particionamento, distribuição, formatos, compressão e padrão de consulta.

Data warehouses precisam de modelagem, governança, particionamento, compressão, controle de custo e clareza sobre quais perguntas precisam responder.

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

**Relação com Data Lake**

Muitas arquiteturas usam [[Amazon S3]] como data lake e [[Amazon Redshift]] como motor analítico.

[[Amazon S3|S3]] armazena dados brutos, históricos e processados. Redshift executa consultas analíticas estruturadas.
