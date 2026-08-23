Multi-AZ é um padrão de alta disponibilidade em que recursos são distribuídos entre múltiplas [[Availability Zones (AZ)]].

No contexto de [[Amazon RDS]], Multi-AZ reduz indisponibilidade ao manter capacidade de recuperação em outra zona.

Multi-AZ deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

Multi-AZ deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

Multi-AZ existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**Objetivo**

O objetivo é proteger contra falhas locais.

Se uma zona ou instância falhar, o serviço pode realizar [[Failover]] para outra zona.

---

## Exemplo prático

Um banco [[Amazon RDS|RDS]] Multi-AZ pode ter uma instância primária em uma AZ e uma instância standby em outra.

Quando ocorre falha, o endpoint do banco pode apontar para a instância promovida.

Uma aplicação de pedidos pode usar:

* [[Amazon RDS]] para transações;
* [[Amazon DynamoDB]] para acesso por chave em alta escala;
* [[Amazon ElastiCache]] para reduzir latência;
* [[Amazon Redshift]] para análise;
* [[Amazon S3]] como data lake.

Cada banco resolve um tipo de problema.

---

## Diferenças importantes

**Diferença para Read Replica**

[[Read Replicas]] servem principalmente para escala de leitura.

Multi-AZ serve principalmente para disponibilidade.

**Como Diferenciar**

* [[Amazon RDS|RDS]]/Aurora: relacional e transacional.
* [[Amazon DynamoDB|DynamoDB]]: NoSQL chave-valor/documento.
* ElastiCache: cache em memória.
* Redshift: data warehouse.
* Neptune: grafos.
* Timestream: séries temporais.

---

## Cuidados

Multi-AZ aumenta resiliência, mas não substitui backup, testes de recuperação e desenho de aplicação tolerante a falhas.

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

**Relação com Arquitetura**

Multi-AZ precisa ser combinado com aplicações que toleram reconexão, retry e pequenos períodos de failover.

- [[Availability Zones (AZ)]]
- [[Amazon RDS]]
- [[Failover]]
- [[Amazon DynamoDB]]
- [[Amazon ElastiCache]]
- [[Amazon Redshift]]
- [[Amazon S3]]
- [[Read Replicas]]
