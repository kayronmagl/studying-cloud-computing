Amazon OpenSearch Service é o serviço gerenciado da AWS para busca, análise textual, logs e observabilidade baseada em índices.

Ele é baseado no ecossistema OpenSearch.

Amazon OpenSearch Service deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Amazon OpenSearch Service deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

Amazon OpenSearch Service existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**Uso**

* busca textual;
* análise de logs;
* dashboards;
* investigação operacional;
* pesquisa em documentos;
* autocomplete;
* analytics quase em tempo real.

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

**Diferença para Banco Relacional**

[[Amazon RDS]] é melhor para transações relacionais.

OpenSearch é melhor para busca textual, indexação e análise exploratória.

**Diferença para Banco Principal**

OpenSearch normalmente não deve ser a única fonte da verdade de dados transacionais.

A fonte primária pode estar em [[Amazon RDS]], [[Amazon DynamoDB]] ou outro banco, enquanto OpenSearch recebe cópias indexadas para busca e análise.

**Como Diferenciar**

* [[Amazon RDS|RDS]]/Aurora: relacional e transacional.
* [[Amazon DynamoDB|DynamoDB]]: NoSQL chave-valor/documento.
* ElastiCache: cache em memória.
* Redshift: data warehouse.
* Neptune: grafos.
* Timestream: séries temporais.

---

## Cuidados

OpenSearch não deve ser fonte primária única de dados transacionais.

Normalmente, ele indexa dados vindos de outra fonte.

Índices precisam ser planejados. Sem estratégia de shards, retenção, mapeamento e ciclo de vida, o cluster pode ficar caro, lento e difícil de operar.

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

**Relação com Logs e Busca**

[[Amazon OpenSearch Service]] é muito usado para busca textual, indexação de documentos, análise de logs e exploração quase em tempo real.

Ele se conecta bem com [[Amazon CloudWatch]], pipelines de observabilidade, aplicações que precisam de busca livre e sistemas que analisam eventos textuais.
