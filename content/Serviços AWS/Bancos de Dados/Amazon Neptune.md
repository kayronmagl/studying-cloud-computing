Amazon Neptune é o serviço de banco de grafos da AWS.

Ele é usado quando o dado principal é formado por entidades e relacionamentos complexos.

Amazon Neptune deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Amazon Neptune deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

Amazon Neptune existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**Modelo**

Em grafos, dados são representados por nós e arestas.

Exemplos:

* pessoas e amizades;
* produtos e recomendações;
* fraudes e conexões;
* redes de dependência;
* conhecimento e entidades.

**Como entender isso na prática**

Neptune não é serviço de transferência de dados.

Quando o cenário envolve grafo, relacionamento entre entidades, nós e arestas, Neptune costuma ser a associação mais direta.

Quando o cenário envolve 100 PB de transferência para AWS, a resposta é [[AWS Snowmobile]].

**Modelo de grafo**

[[Bancos de Dados de Grafos]] explicam o tipo de problema em que o Amazon Neptune faz sentido, como relações entre entidades.

---

## Exemplo prático

Uma aplicação de pedidos pode usar:

* [[Amazon RDS]] para transações;
* [[Amazon DynamoDB]] para acesso por chave em alta escala;
* [[Amazon ElastiCache]] para reduzir latência;
* [[Amazon Redshift]] para análise;
* [[Amazon S3]] como data lake.

Cada banco resolve um tipo de problema.

Um banco de grafos pode responder perguntas como:

* quais contas estão conectadas ao mesmo dispositivo?
* qual caminho liga entidade A à entidade B?
* quais produtos estão relacionados por comportamento de compra?

---

## Diferenças importantes

**Quando Usar**

Use quando a pergunta importante envolve caminhos, conexões e relações profundas.

Exemplo:

* quais contas estão conectadas ao mesmo dispositivo?
* qual cadeia de entidades liga A a B?
* quais produtos se relacionam por padrões de compra?

**Diferença para Relacional**

Um banco relacional consegue representar relações, mas consultas de múltiplos saltos podem ficar complexas e caras.

Um banco de grafos é otimizado para navegar relações.

**Como Diferenciar**

* [[Amazon RDS|RDS]]/Aurora: relacional e transacional.
* [[Amazon DynamoDB|DynamoDB]]: NoSQL chave-valor/documento.
* ElastiCache: cache em memória.
* Redshift: data warehouse.
* Neptune: grafos.
* Timestream: séries temporais.

---

## Cuidados

Não use grafo apenas por sofisticação.

Use quando consultas de relacionamento são centrais para o problema.

A escolha do banco deve partir do padrão de acesso.

Perguntas importantes:

* preciso de transação?
* preciso de join?
* preciso de baixa latência por chave?
* preciso de analytics?
* preciso de relacionamento em grafo?

Escolher banco só pelo nome do serviço costuma gerar arquitetura ruim.

NoSQL não é “sem modelagem”. Em [[Amazon DynamoDB|DynamoDB]], modelagem é orientada pelas consultas.

Amazon Neptune é o serviço de banco de grafos da AWS.

Ele é usado para dados em que relacionamentos são o centro do problema, como redes sociais, recomendações, detecção de fraude, grafos de conhecimento e dependências.

Neptune pode armazenar muitos dados, mas sua função é banco de grafos, não migração física massiva.

---

## Relação com outras notas

- [[AWS Snowmobile]]
- [[Bancos de Dados de Grafos]]
- [[Amazon RDS]]
- [[Amazon DynamoDB]]
- [[Amazon ElastiCache]]
- [[Amazon Redshift]]
- [[Amazon S3]]
