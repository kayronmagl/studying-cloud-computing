Bancos de Dados Relacionais organizam dados em tabelas, linhas, colunas e relações.

O modelo relacional foi formalizado por Edgar F. Codd em 1970 e se tornou uma das bases da computação corporativa. A ideia central é representar dados em relações matemáticas, permitindo integridade, consulta declarativa e consistência.

## Estrutura

Um banco relacional usa:

* tabelas;
* colunas;
* linhas;
* chaves primárias;
* chaves estrangeiras;
* índices;
* constraints;
* transações;
* SQL.

Exemplo: uma tabela `clientes` pode se relacionar com uma tabela `pedidos`, e `pedidos` pode se relacionar com `pagamentos`.

---

## SQL

SQL significa Structured Query Language.

É a linguagem usada para consultar e manipular dados relacionais.

Exemplo conceitual:

```sql
SELECT * FROM pedidos WHERE cliente_id = 10;
```

SQL permite filtros, joins, agregações, ordenações e transações.

---

## Transações ACID

Bancos relacionais são fortes quando a aplicação precisa de [[Transações ACID]].

Isso é essencial em pedidos, pagamentos, estoque, contratos, faturamento e sistemas onde inconsistência gera prejuízo.

---

## Relação com AWS

Na AWS, os serviços relacionais principais são:

* [[Amazon RDS]];
* [[Amazon Aurora]].

Eles reduzem operação, mas não eliminam a necessidade de modelagem, índices, análise de queries e desenho de consistência.

---

## Quando Usar

Use banco relacional quando os dados têm estrutura clara, relações importantes e necessidade de consistência forte.

Não use NoSQL apenas por moda. A escolha deve seguir o padrão de acesso e as garantias necessárias.

---

## Exemplo Prático

Imagine um sistema de pedidos. Um cliente faz uma compra, o pedido precisa ser registrado, o estoque precisa diminuir e o pagamento precisa ser associado à mesma operação. Um banco relacional ajuda porque permite representar clientes, pedidos, itens e pagamentos em tabelas diferentes, mantendo relações explícitas entre elas.

Essa estrutura facilita consultas como “quais pedidos pertencem a este cliente?”, “quais itens fazem parte deste pedido?” ou “qual pagamento confirma esta compra?”. O valor do modelo relacional aparece justamente quando a integridade entre entidades importa.

---

## Cuidados importantes

Um erro comum é tratar banco relacional como tecnologia antiga e NoSQL como substituto automático. Bancos relacionais continuam adequados quando o domínio tem relações importantes, regras de integridade, consultas estruturadas e transações. O problema não é usar relacional ou NoSQL, mas escolher sem entender o padrão de dados e as garantias exigidas pela aplicação.
