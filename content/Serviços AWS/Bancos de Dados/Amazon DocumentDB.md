Amazon DocumentDB é um serviço de banco de documentos da AWS com compatibilidade com MongoDB.

Ele armazena dados em formato documental, geralmente JSON-like, permitindo estruturas flexíveis.

Amazon DocumentDB deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Amazon DocumentDB deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

Amazon DocumentDB existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**Modelo de Documento**

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

Use para:

* catálogos;
* perfis;
* documentos com estrutura variável;
* conteúdo sem esquema rígido;
* aplicações que já usam [[APIs|APIs]] MongoDB compatíveis.

**Diferença para [[Amazon DynamoDB|DynamoDB]]**

[[Amazon DynamoDB]] é chave-valor/documento altamente escalável e orientado a padrões de acesso.

DocumentDB se aproxima mais do modelo de documentos compatível com MongoDB.

**Como Diferenciar**

* [[Amazon RDS|RDS]]/Aurora: relacional e transacional.
* [[Amazon DynamoDB|DynamoDB]]: NoSQL chave-valor/documento.
* ElastiCache: cache em memória.
* Redshift: data warehouse.
* Neptune: grafos.
* Timestream: séries temporais.

---

## Cuidados

Flexibilidade de documento não elimina modelagem.

Documentos grandes, duplicação sem critério e consultas sem índice podem prejudicar performance.

A escolha do banco deve partir do padrão de acesso.

Perguntas importantes:

* preciso de transação?
* preciso de join?
* preciso de baixa latência por chave?
* preciso de analytics?
* preciso de relacionamento em grafo?

Escolher banco só pelo nome do serviço costuma gerar arquitetura ruim.

NoSQL não é “sem modelagem”. Em [[Amazon DynamoDB|DynamoDB]], modelagem é orientada pelas consultas.

---

## Relação com outras notas

- [[Amazon RDS]]
- [[Amazon DynamoDB]]
- [[Amazon ElastiCache]]
- [[Amazon Redshift]]
- [[Amazon S3]]
