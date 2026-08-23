Bancos de Dados de Séries Temporais são bancos otimizados para dados indexados pelo tempo.

Eles armazenam medições, eventos e métricas que fazem sentido em sequência temporal.

Bancos de Dados de Séries Temporais deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Bancos de Dados de Séries Temporais deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

Bancos de Dados de Séries Temporais existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**AWS**

Na AWS, o serviço principal é o [[Amazon Timestream]].

**Padrão de Consulta**

Bancos de séries temporais são desenhados para perguntas como:

* qual foi a média nos últimos 5 minutos?
* qual sensor passou do limite?
* qual métrica cresceu por hora?
* qual tendência apareceu na semana?

O tempo é parte central do dado.

---

## Exemplo prático

* métricas de CPU;
* sensores IoT;
* telemetria;
* logs estruturados;
* preços ao longo do tempo;
* eventos de monitoramento.

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

A modelagem precisa considerar retenção, granularidade, agregações e volume de ingestão.

Nem todo dado com timestamp exige banco de séries temporais. Se o volume é pequeno e as consultas são relacionais, [[Amazon RDS]] pode bastar.

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

**Relação com Timestream**

Na AWS, [[Amazon Timestream]] é o serviço criado para esse modelo.

Ele é útil para IoT, telemetria, métricas operacionais, dados industriais e medições frequentes.
