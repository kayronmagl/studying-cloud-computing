Bancos de Dados de Grafos armazenam dados como nós e relacionamentos.

Eles são adequados quando a relação entre entidades é tão importante quanto as entidades.


Bancos de Dados de Grafos deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Usos

* recomendação;
* fraude;
* redes sociais;
* dependências;
* identidade;
* conhecimento;
* rotas e conexões.

---

## AWS

Na AWS, o serviço gerenciado principal é o [[Amazon Neptune]].

---

## Cuidado

Não use grafo apenas porque parece sofisticado.

Use quando as consultas realmente dependem de navegação por relacionamentos.

---

## Quando o Grafo é Melhor

Um grafo é forte quando a pergunta envolve caminhos e relacionamentos.

Exemplo:


* quais contas estão conectadas ao mesmo dispositivo?
* quais produtos são comprados juntos?
* qual rota conecta dois pontos?
* quais entidades compartilham intermediários?


Essas perguntas podem ficar complexas em bancos relacionais quando exigem muitos saltos.

---

## Relação com Neptune

Na AWS, [[Amazon Neptune]] é o serviço gerenciado para grafos.

Ele deve ser escolhido quando o relacionamento é o centro do problema, não apenas um detalhe.

---

## Cuidado na prática

Se as consultas são simples e tabulares, um banco relacional pode ser suficiente. Grafo agrega valor quando a navegação por relações é frequente e crítica.

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
