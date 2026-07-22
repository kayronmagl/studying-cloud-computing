Multi-AZ é um padrão de alta disponibilidade em que recursos são distribuídos entre múltiplas [[Availability Zones (AZ)]].

No contexto de [[Amazon RDS]], Multi-AZ reduz indisponibilidade ao manter capacidade de recuperação em outra zona.


Multi-AZ deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## Objetivo

O objetivo é proteger contra falhas locais.

Se uma zona ou instância falhar, o serviço pode realizar [[Failover]] para outra zona.

---

## Diferença para Read Replica

[[Read Replicas]] servem principalmente para escala de leitura.

Multi-AZ serve principalmente para disponibilidade.

---

## Exemplo

Um banco RDS Multi-AZ pode ter uma instância primária em uma AZ e uma instância standby em outra.

Quando ocorre falha, o endpoint do banco pode apontar para a instância promovida.

---

## Relação com Arquitetura

Multi-AZ precisa ser combinado com aplicações que toleram reconexão, retry e pequenos períodos de failover.

---

## Cuidado

Multi-AZ aumenta resiliência, mas não substitui backup, testes de recuperação e desenho de aplicação tolerante a falhas.

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
