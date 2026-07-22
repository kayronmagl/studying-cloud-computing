Bancos de Dados são sistemas especializados em armazenar, organizar, consultar, proteger e recuperar informações de forma confiável.

Eles existem porque aplicações reais precisam preservar estado. Um sistema de vendas precisa guardar pedidos. Uma rede social precisa guardar perfis e relações. Um sistema financeiro precisa registrar transações. Uma aplicação de streaming precisa guardar metadados, histórico e preferências.

Um banco de dados não é apenas um lugar onde dados ficam parados. Ele oferece mecanismos para consulta, indexação, concorrência, consistência, segurança, backup e recuperação.

## Diferença entre Arquivo e Banco de Dados

Um arquivo simples pode guardar informação, mas não resolve bem problemas como:

* múltiplos usuários escrevendo ao mesmo tempo;
* busca eficiente;
* integridade entre entidades;
* controle de transações;
* recuperação após falha;
* auditoria;
* permissões;
* concorrência;
* índices.

Bancos de dados foram criados para resolver esses problemas de forma sistemática.

---

## Modelos Principais

Os [[Bancos de Dados Relacionais]] organizam dados em tabelas, linhas, colunas e relações. Eles são fortes quando há necessidade de consistência, integridade e consultas estruturadas.

Os [[NoSQL]] foram criados para modelos mais flexíveis, grande escala horizontal e padrões específicos de acesso, como chave-valor, documento, colunas largas e grafos.

Na AWS, isso aparece em serviços como:

* [[Amazon RDS]];
* [[Amazon Aurora]];
* [[Amazon DynamoDB]];
* [[Amazon DocumentDB]];
* [[Amazon Neptune]];
* [[Amazon Timestream]];
* [[Amazon Redshift]].

---

## Transações

Em sistemas críticos, não basta gravar dados. É necessário garantir que operações compostas não deixem o sistema em estado inconsistente.

Exemplo: em uma compra, o sistema pode precisar reduzir estoque, registrar pagamento e criar pedido. Se apenas uma parte for concluída, o sistema fica corrompido.

É por isso que [[Transações ACID]] são importantes em bancos relacionais.

---

## Banco Gerenciado na Nuvem

Na nuvem, o banco pode ser autogerenciado ou gerenciado.

No modelo autogerenciado, a equipe instala o banco em [[Amazon EC2]], cuida do sistema operacional, patches, backup, replicação e monitoramento.

No modelo gerenciado, serviços como [[Amazon RDS]] e [[Amazon Aurora]] assumem parte da operação. A equipe continua responsável por modelagem, índices, queries, permissões, rede, custo e uso correto.

---

## Relação com Armazenamento

Banco de dados não é sinônimo de armazenamento.

[[Amazon S3]] armazena objetos. [[Amazon EBS]] fornece blocos. [[Amazon EFS]] fornece arquivos. Bancos de dados organizam dados com semântica de consulta, consistência e concorrência.

Essa diferença evita o erro de tentar resolver todo problema de persistência com o mesmo serviço.

---

## Exemplo

Em uma aplicação de pedidos, o banco precisa guardar clientes, produtos, estoque, pagamentos e o estado de cada compra. Quando o usuário confirma o pedido, a aplicação não está apenas salvando um texto em algum lugar. Ela precisa preservar relações, impedir gravações conflitantes, consultar dados rapidamente e permitir recuperação se algo falhar.

Na nuvem, o provedor pode facilitar a criação do banco, automatizar backups, oferecer réplicas e expor métricas. Ainda assim, a equipe precisa escolher o modelo de dados, desenhar índices, configurar permissões, controlar custo e entender como a aplicação acessa as informações.

---

## Erros Comuns

Um erro comum é escolher banco de dados pelo nome do serviço, e não pelo formato do problema. Um sistema que precisa de transações fortes, relações claras e consultas com joins pode se encaixar melhor em um banco relacional. Um sistema que consulta sempre por chave, aceita modelagem orientada ao acesso e precisa escalar horizontalmente pode se encaixar melhor em um modelo NoSQL.

Outro erro é confundir armazenamento com banco de dados. Um serviço de armazenamento guarda bytes, arquivos ou objetos. Um banco de dados acrescenta regras de consulta, concorrência, consistência e recuperação.

---

## Bancos gerenciados na AWS

[[Bancos de Dados da AWS]] reúne os principais serviços gerenciados usados para diferentes modelos de dados.
