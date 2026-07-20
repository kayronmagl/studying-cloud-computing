Bancos de Dados de Séries Temporais são bancos otimizados para dados indexados pelo tempo.

Eles armazenam medições, eventos e métricas que fazem sentido em sequência temporal.

---

## Visão geral

Bancos de Dados de Séries Temporais deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Exemplos

* métricas de CPU;
* sensores IoT;
* telemetria;
* logs estruturados;
* preços ao longo do tempo;
* eventos de monitoramento.

---

## AWS

Na AWS, o serviço principal é o [[Amazon Timestream]].

---

## Cuidado

A modelagem precisa considerar retenção, granularidade, agregações e volume de ingestão.

---

## Padrão de Consulta

Bancos de séries temporais são desenhados para perguntas como:


* qual foi a média nos últimos 5 minutos?
* qual sensor passou do limite?
* qual métrica cresceu por hora?
* qual tendência apareceu na semana?


O tempo é parte central do dado.

---

## Relação com Timestream

Na AWS, [[Amazon Timestream]] é o serviço criado para esse modelo.

Ele é útil para IoT, telemetria, métricas operacionais, dados industriais e medições frequentes.

---

## Cuidado na prática

Nem todo dado com timestamp exige banco de séries temporais. Se o volume é pequeno e as consultas são relacionais, [[Amazon RDS]] pode bastar.

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
