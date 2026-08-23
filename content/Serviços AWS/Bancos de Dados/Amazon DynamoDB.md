Amazon DynamoDB é um banco NoSQL gerenciado da AWS, orientado a chave-valor e documento.

Ele é projetado para baixa latência e alta escala, especialmente quando o padrão de acesso é conhecido antecipadamente.

Amazon DynamoDB deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

Muitas alternativas erradas parecem boas quando o padrão de acesso é ignorado.

---

## O que é

Amazon DynamoDB é banco NoSQL gerenciado, chave-valor/documento, projetado para baixa latência e alta escala.

DynamoDB é NoSQL gerenciado, orientado a chave-valor e documento. Isso significa que ele não é usado como uma planilha SQL tradicional com joins como centro do desenho. Ele organiza dados em tabelas, itens e atributos.

Ele é usado quando a aplicação precisa de baixa latência, escala e acesso por chave.

Para um iniciante, a ideia principal é: em DynamoDB, você precisa saber antes como a aplicação vai buscar os dados. O desenho da tabela nasce do padrão de acesso.

---

## Por que existe

Amazon DynamoDB existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**Modelo**

DynamoDB organiza dados em tabelas.

Cada item possui chave primária e atributos.

A modelagem começa pelas consultas que a aplicação precisa responder.

**Conceitos Essenciais**

* partition key;
* sort key;
* tabela;
* item;
* atributos;
* índices secundários;
* capacidade sob demanda ou provisionada.

**Tradução dos termos**

* Tabela: conjunto de itens.
* Item: registro individual dentro da tabela.
* Atributo: campo dentro de um item.
* Partition key: parte obrigatória da chave primária que distribui os dados internamente.
* Sort key: parte opcional da chave primária que ordena ou diferencia itens dentro da mesma partition key.
* Índice secundário: estrutura adicional para consultar dados por outro caminho.

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

**Diferença para Relacional**

Em [[Bancos de Dados Relacionais]], é comum modelar entidades normalizadas e consultar com joins.

Em DynamoDB, o desenho é orientado por chave, partição, sort key, índices e padrões de acesso.

**Quando Usar**

* sessões;
* carrinhos;
* perfis;
* metadados;
* catálogos;
* eventos;
* workloads serverless;
* baixa latência em escala.

**Quando Usar na prática**

Use quando o padrão de acesso é conhecido e baseado em chave, com necessidade de escala e baixa latência.

**Pontos que Costumam Gerar Confusão**

Quando o cenário envolve banco de dados chave-valor, a resposta é [[Amazon DynamoDB]].

**Comparação**

* DynamoDB: chave-valor/documento.
* [[Amazon Aurora|Aurora]]: relacional compatível com MySQL/PostgreSQL.
* [[Amazon RDS|RDS]]: bancos relacionais gerenciados.
* DocumentDB: documentos compatíveis com MongoDB.

---

## Cuidados

DynamoDB exige boa modelagem de chave.

Usar como se fosse SQL costuma gerar scans caros, baixa eficiência e desenho ruim.

A escolha do banco deve partir do padrão de acesso.

Perguntas importantes:

* preciso de transação?
* preciso de join?
* preciso de baixa latência por chave?
* preciso de analytics?
* preciso de relacionamento em grafo?

Escolher banco só pelo nome do serviço costuma gerar arquitetura ruim.

DynamoDB exige modelagem por padrão de acesso. Não é “[[Amazon RDS|RDS]] sem tabela”. Consultas precisam ser pensadas antes.

Evite explicar DynamoDB apenas como “banco rápido”. O ponto técnico é mais específico: ele é eficiente quando a modelagem combina com as consultas. Se a aplicação precisa fazer consultas livres, muitos relacionamentos e joins complexos, um banco relacional pode ser mais adequado.

---

## Relação com outras notas

**Relação com Gestão Financeira**

* [[Amazon DynamoDB sob Demanda]];

- [[Bancos de Dados NoSQL]]
- [[NoSQL]]
- [[Amazon RDS]]
- [[Amazon Aurora]]
- [[Amazon SQS]]
