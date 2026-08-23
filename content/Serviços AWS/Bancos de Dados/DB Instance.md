Uma DB Instance é a unidade operacional básica do [[Amazon RDS]].

Ela representa um ambiente de banco gerenciado com motor, classe de instância, armazenamento, endpoint, porta, parâmetros, backups e configurações de rede.

DB Instance deve ser estudado a partir do padrão de acesso. Antes de escolher um banco, pergunte como a aplicação vai consultar, gravar, escalar e manter consistência.

muitas alternativas erradas parecem boas porque ignoram esse padrão de acesso.

---

## O que é

DB Instance deve ser entendido pelo modelo de dados, pelo padrão de consulta e pela consistência exigida. Banco de dados na nuvem não é apenas onde a informação fica guardada; é onde leitura, escrita, escala, backup, latência e custo se encontram.

A escolha do banco depende do padrão de acesso, consistência, escala, consulta e modelo de dados.

---

## Por que existe

DB Instance existe para resolver necessidades de persistência, consulta, consistência, escala ou especialização de dados. Escolher banco errado pode gerar custo alto, lentidão, modelagem confusa e dificuldade para manter a aplicação.

---

## Como funciona

**Componentes**

Uma DB Instance possui:

* motor;
* classe;
* armazenamento;
* usuário mestre;
* endpoint;
* porta;
* subnet group;
* security group;
* backups;
* parâmetros;
* janela de manutenção.

**Operação**

O [[Amazon RDS|RDS]] gerencia parte da operação, como provisionamento, backups automáticos e manutenção do serviço.

O cliente ainda cuida de schema, índices, queries, usuários do banco, parâmetros e acesso de rede.

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

**Como Diferenciar**

* [[Amazon RDS|RDS]]/Aurora: relacional e transacional.
* [[Amazon DynamoDB|DynamoDB]]: NoSQL chave-valor/documento.
* ElastiCache: cache em memória.
* Redshift: data warehouse.
* Neptune: grafos.
* Timestream: séries temporais.

---

## Cuidados

DB Instance não é apenas “um banco”.

É um recurso gerenciado que participa da arquitetura de rede, segurança, backup, disponibilidade e custo.

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

**Relação com [[Amazon VPC|VPC]]**

DB Instances normalmente ficam dentro de uma [[Amazon VPC]], muitas vezes em sub-redes privadas.

Isso impede exposição direta à internet e permite acesso apenas por aplicações autorizadas.
