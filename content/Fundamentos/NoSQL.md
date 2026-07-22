NoSQL é uma família de bancos de dados não relacionais criada para modelos de dados e padrões de escala que nem sempre se encaixam bem no modelo relacional tradicional.

O termo não significa ausência total de estrutura. Significa que o banco não segue necessariamente o modelo de tabelas relacionais com SQL como forma principal de acesso.

## Por que Surgiu

Com aplicações web de grande escala, surgiram problemas como:

* alto volume de escrita;
* dados sem esquema fixo;
* distribuição horizontal;
* baixa latência em escala;
* grandes volumes de eventos;
* consultas por chave;
* necessidade de flexibilidade.

Bancos relacionais continuam fortes, mas nem sempre são a melhor ferramenta para esses casos.

---

## Modelos NoSQL

Existem vários modelos:

* chave-valor;
* documento;
* colunas largas;
* grafos;
* séries temporais.

Na AWS, exemplos incluem [[Amazon DynamoDB]], [[Amazon DocumentDB]], [[Amazon Keyspaces]], [[Amazon Neptune]] e [[Amazon Timestream]].

---

## Modelagem

NoSQL exige modelagem.

Em muitos bancos NoSQL, o desenho começa pelas perguntas que a aplicação precisa responder.

Exemplo: no [[Amazon DynamoDB]], uma tabela mal modelada pode gerar scans caros e baixa performance.

---

## Trade-off

NoSQL pode oferecer escala e flexibilidade, mas pode abrir mão de algumas facilidades relacionais, como joins complexos e transações amplas.

A escolha correta depende do padrão de acesso.

---

## Exemplo Prático

Imagine uma aplicação que precisa buscar rapidamente o perfil de um usuário por identificador. Se o padrão principal de acesso é “dado este ID, recupere este documento”, um banco de documentos ou chave-valor pode ser mais simples e eficiente do que espalhar os mesmos dados em várias tabelas e fazer joins a cada leitura.

O raciocínio muda quando a aplicação precisa de relatórios complexos, relações ricas entre várias entidades ou transações amplas. Nesses casos, a flexibilidade do NoSQL pode virar custo de modelagem e operação. A escolha precisa partir das perguntas que a aplicação fará aos dados.

---

## Cuidados importantes

NoSQL não significa “sem regras” nem “sempre mais rápido”. Muitos bancos NoSQL exigem modelagem cuidadosa, definição clara de chaves, entendimento de consistência e atenção aos custos de leitura e escrita. O ganho costuma aparecer quando o modelo escolhido combina com o padrão real de acesso.

## Tipos de bancos NoSQL

[[Bancos de Dados NoSQL]] aprofundam os modelos não relacionais que aparecem em serviços como DynamoDB, DocumentDB e Neptune.
