Amazon DocumentDB é um serviço de banco de documentos da AWS com compatibilidade com MongoDB.

Ele armazena dados em formato documental, geralmente JSON-like, permitindo estruturas flexíveis.


Amazon DocumentDB deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Modelo de Documento

Em vez de dividir tudo em tabelas normalizadas, um documento pode agregar campos relacionados.

Exemplo conceitual:

```json
{
  "cliente": "Ana",
  "enderecos": [
    {"cidade": "Fortaleza", "tipo": "entrega"}
  ]
}
```

---

## Quando Usar

Use para:

* catálogos;
* perfis;
* documentos com estrutura variável;
* conteúdo sem esquema rígido;
* aplicações que já usam APIs MongoDB compatíveis.

---

## Diferença para DynamoDB

[[Amazon DynamoDB]] é chave-valor/documento altamente escalável e orientado a padrões de acesso.

DocumentDB se aproxima mais do modelo de documentos compatível com MongoDB.

---

## Cuidado

Flexibilidade de documento não elimina modelagem.

Documentos grandes, duplicação sem critério e consultas sem índice podem prejudicar performance.

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
