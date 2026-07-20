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

Imagine uma aplicação web simples. Ela precisa receber requisições, processar dados, gravar informações, proteger acesso e responder ao usuário.

Mesmo usando AWS, a aplicação ainda depende de conceitos como rede, protocolo, servidor, banco, API e armazenamento. A diferença é que muitos desses elementos deixam de ser comprados e instalados manualmente e passam a ser configurados por serviço.

---

## Cuidados importantes

O erro comum é decorar o nome do serviço sem entender o fundamento. Isso gera confusão, por exemplo, ao comparar banco relacional com NoSQL, servidor físico com instância virtual, ou API com interface gráfica.

Por isso, esta nota deve funcionar como camada de apoio para entender os módulos posteriores.

## Tipos de bancos NoSQL

[[Bancos de Dados NoSQL]] aprofundam os modelos não relacionais que aparecem em serviços como DynamoDB, DocumentDB e Neptune.
