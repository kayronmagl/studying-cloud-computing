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

Imagine uma aplicação web simples. Ela precisa receber requisições, processar dados, gravar informações, proteger acesso e responder ao usuário.

Mesmo usando AWS, a aplicação ainda depende de conceitos como rede, protocolo, servidor, banco, API e armazenamento. A diferença é que muitos desses elementos deixam de ser comprados e instalados manualmente e passam a ser configurados por serviço.

---

## Cuidados importantes

O erro comum é decorar o nome do serviço sem entender o fundamento. Isso gera confusão, por exemplo, ao comparar banco relacional com NoSQL, servidor físico com instância virtual, ou API com interface gráfica.

Por isso, esta nota deve funcionar como camada de apoio para entender os módulos posteriores.
