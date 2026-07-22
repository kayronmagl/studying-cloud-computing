Amazon DynamoDB é um banco NoSQL gerenciado da AWS, orientado a chave-valor e documento.

Ele é projetado para baixa latência e alta escala, especialmente quando o padrão de acesso é conhecido antecipadamente.


Amazon DynamoDB deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Modelo

DynamoDB organiza dados em tabelas.

Cada item possui chave primária e atributos.

A modelagem começa pelas consultas que a aplicação precisa responder.

---

## Diferença para Relacional

Em [[Bancos de Dados Relacionais]], é comum modelar entidades normalizadas e consultar com joins.

Em DynamoDB, o desenho é orientado por chave, partição, sort key, índices e padrões de acesso.

---

## Quando Usar

* sessões;
* carrinhos;
* perfis;
* metadados;
* catálogos;
* eventos;
* workloads serverless;
* baixa latência em escala.

---

## Cuidado

DynamoDB exige boa modelagem de chave.

Usar como se fosse SQL costuma gerar scans caros, baixa eficiência e desenho ruim.

---

## Relação com Gestão Financeira

* [[Amazon DynamoDB sob Demanda]];

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

## Explicação principal

Amazon DynamoDB é banco NoSQL gerenciado, chave-valor/documento, projetado para baixa latência e alta escala.

## Conceitos Essenciais

* partition key;
* sort key;
* tabela;
* item;
* atributos;
* índices secundários;
* capacidade sob demanda ou provisionada.

## Quando Usar na prática

Use quando o padrão de acesso é conhecido e baseado em chave, com necessidade de escala e baixa latência.

## Cuidado importante

DynamoDB exige modelagem por padrão de acesso. Não é “RDS sem tabela”. Consultas precisam ser pensadas antes.

---

## Pontos que Costumam Gerar Confusão

Quando o cenário envolve banco de dados chave-valor, a resposta é [[Amazon DynamoDB]].

---

## Como entender

DynamoDB é NoSQL gerenciado, orientado a chave-valor e documento.

Ele é usado quando a aplicação precisa de baixa latência, escala e acesso por chave.

---

## Comparação

* DynamoDB: chave-valor/documento.
* [[Amazon Aurora|Aurora]]: relacional compatível com MySQL/PostgreSQL.
* [[Amazon RDS|RDS]]: bancos relacionais gerenciados.
* DocumentDB: documentos compatíveis com MongoDB.
