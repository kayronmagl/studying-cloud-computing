Amazon Keyspaces é o serviço gerenciado da AWS compatível com Apache Cassandra.

Ele é usado para workloads que precisam do modelo de colunas largas e compatibilidade com Cassandra Query Language.

Amazon Keyspaces deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Amazon Keyspaces deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

---

## Por que existe

Amazon Keyspaces existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**Trade-offs**

A vantagem é reduzir operação de Cassandra autogerenciado. A desvantagem é que o modelo de dados continua exigente: partições mal desenhadas podem gerar hotspots, consultas ineficientes e custo desnecessário.

Para workloads relacionais, [[Amazon RDS]] ou [[Amazon Aurora]] continuam sendo opções mais naturais.

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

**Quando Usar**

* workloads já baseados em Cassandra;
* alta escala de escrita;
* tabelas largas;
* baixa latência;
* aplicações distribuídas.

---

## Cuidados

Não escolha apenas por ser NoSQL.

O modelo Cassandra exige boa definição de partição, chave e padrão de consulta.

A escolha do banco deve partir do padrão de acesso.

Perguntas importantes:

* preciso de transação?
* preciso de join?
* preciso de baixa latência por chave?
* preciso de analytics?
* preciso de relacionamento em grafo?

Escolher banco só pelo nome do serviço costuma gerar arquitetura ruim.

---

## Relação com outras notas

**Relação com Bancos Purpose-Built**

[[Amazon Keyspaces]] faz sentido quando o modelo Cassandra já é uma exigência técnica ou quando o padrão de acesso favorece colunas largas, alta escala de escrita e consultas desenhadas por chave.

Ele não deve ser usado apenas porque é NoSQL. Assim como [[Amazon DynamoDB]], exige modelagem orientada a consulta. A aplicação precisa saber antecipadamente como os dados serão buscados.
