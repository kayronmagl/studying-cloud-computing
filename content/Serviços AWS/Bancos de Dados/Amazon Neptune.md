Amazon Neptune é o serviço de banco de grafos da AWS.

Ele é usado quando o dado principal é formado por entidades e relacionamentos complexos.

---

## Visão geral

Amazon Neptune deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Modelo

Em grafos, dados são representados por nós e arestas.

Exemplos:

* pessoas e amizades;
* produtos e recomendações;
* fraudes e conexões;
* redes de dependência;
* conhecimento e entidades.

---

## Quando Usar

Use quando a pergunta importante envolve caminhos, conexões e relações profundas.

Exemplo:


* quais contas estão conectadas ao mesmo dispositivo?
* qual cadeia de entidades liga A a B?
* quais produtos se relacionam por padrões de compra?


---

## Diferença para Relacional

Um banco relacional consegue representar relações, mas consultas de múltiplos saltos podem ficar complexas e caras.

Um banco de grafos é otimizado para navegar relações.

---

## Cuidado

Não use grafo apenas por sofisticação.

Use quando consultas de relacionamento são centrais para o problema.

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

---

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

---

Amazon Neptune é o serviço de banco de grafos da AWS.

Ele é usado para dados em que relacionamentos são o centro do problema, como redes sociais, recomendações, detecção de fraude, grafos de conhecimento e dependências.

---

## Como entender isso na prática

Neptune não é serviço de transferência de dados.

Quando o cenário envolve grafo, relacionamento entre entidades, nós e arestas, Neptune costuma ser a associação mais direta.

Quando o cenário envolve 100 PB de transferência para AWS, a resposta é [[AWS Snowmobile]].

---

## Exemplo

Um banco de grafos pode responder perguntas como:


* quais contas estão conectadas ao mesmo dispositivo?
* qual caminho liga entidade A à entidade B?
* quais produtos estão relacionados por comportamento de compra?


---

## Cuidado importante na prática

Neptune pode armazenar muitos dados, mas sua função é banco de grafos, não migração física massiva.

---

## Modelo de grafo

[[Bancos de Dados de Grafos]] explicam o tipo de problema em que o Amazon Neptune faz sentido, como relações entre entidades.
