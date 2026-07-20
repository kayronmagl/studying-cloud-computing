Amazon Keyspaces é o serviço gerenciado da AWS compatível com Apache Cassandra.

Ele é usado para workloads que precisam do modelo de colunas largas e compatibilidade com Cassandra Query Language.

---

## Visão geral

Amazon Keyspaces deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Quando Usar

* workloads já baseados em Cassandra;
* alta escala de escrita;
* tabelas largas;
* baixa latência;
* aplicações distribuídas.

---

## Cuidado

Não escolha apenas por ser NoSQL.

O modelo Cassandra exige boa definição de partição, chave e padrão de consulta.

---

## Relação com Bancos Purpose-Built

[[Amazon Keyspaces]] faz sentido quando o modelo Cassandra já é uma exigência técnica ou quando o padrão de acesso favorece colunas largas, alta escala de escrita e consultas desenhadas por chave.

Ele não deve ser usado apenas porque é NoSQL. Assim como [[Amazon DynamoDB]], exige modelagem orientada a consulta. A aplicação precisa saber antecipadamente como os dados serão buscados.

---

## Trade-offs

A vantagem é reduzir operação de Cassandra autogerenciado. A desvantagem é que o modelo de dados continua exigente: partições mal desenhadas podem gerar hotspots, consultas ineficientes e custo desnecessário.

Para workloads relacionais, [[Amazon RDS]] ou [[Amazon Aurora]] continuam sendo opções mais naturais.

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
