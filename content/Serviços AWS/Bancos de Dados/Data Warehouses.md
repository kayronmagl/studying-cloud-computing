Data Warehouses são bancos analíticos usados para consolidar e consultar grandes volumes de dados históricos.

Eles são otimizados para leitura, agregação e análise, não para transações pequenas de alta frequência.

---

## Visão geral

Data Warehouses deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## OLTP vs OLAP

OLTP é processamento transacional.

OLAP é processamento analítico.

[[Amazon RDS]] atende melhor OLTP. [[Amazon Redshift]] atende melhor OLAP.

---

## Uso

* BI;
* relatórios;
* métricas históricas;
* análise de vendas;
* auditoria;
* dados consolidados de múltiplas fontes.

---

## Cuidado

Data warehouse mal modelado pode ficar caro e lento.

É preciso pensar em particionamento, distribuição, formatos, compressão e padrão de consulta.

---

## Diferença para Banco Operacional

Um banco operacional atende a aplicação em tempo real.

Um data warehouse atende análise.

Exemplo:


* [[Amazon RDS]]: registrar pedido agora.
* [[Amazon Redshift]]: analisar vendas dos últimos 3 anos.


Misturar essas funções pode gerar lentidão e custo.

---

## Relação com Data Lake

Muitas arquiteturas usam [[Amazon S3]] como data lake e [[Amazon Redshift]] como motor analítico.

S3 armazena dados brutos, históricos e processados. Redshift executa consultas analíticas estruturadas.

---

## Cuidado na prática

Data warehouses precisam de modelagem, governança, particionamento, compressão, controle de custo e clareza sobre quais perguntas precisam responder.

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
