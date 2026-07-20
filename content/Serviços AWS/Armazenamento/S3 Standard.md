S3 Standard é a classe padrão do [[Amazon S3]] para dados acessados com frequência.

Ela é indicada para objetos ativos, como imagens recentes, arquivos estáticos, documentos frequentemente acessados, logs recentes e conteúdo distribuído por [[Amazon CloudFront]].

## Quando Usar

Use quando:

* os dados são acessados frequentemente;
* o padrão de acesso ainda é desconhecido;
* a aplicação precisa de acesso imediato;
* o objeto faz parte do fluxo operacional atual.

---

## Exemplos

* imagens de produtos atuais;
* arquivos de sites;
* documentos usados diariamente;
* exports recentes;
* dados de aplicações ativas.

---

## Trade-off

S3 Standard tende a ter custo de armazenamento maior do que classes frias, mas evita custos e atrasos de recuperação associados a classes de acesso infrequente ou arquivamento.

---

## Migração

Quando os objetos envelhecem e passam a ser acessados raramente, [[S3 Lifecycle]] pode movê-los para [[S3 Standard-IA]], [[S3 Intelligent-Tiering]] ou classes Glacier.

---

## Exemplo Prático

Uma aplicação pode usar:

* [[Amazon EBS]] para disco de uma instância;
* [[Amazon S3]] para objetos e arquivos;
* [[Amazon EFS]] para filesystem compartilhado;
* classes de armazenamento para reduzir custo de dados antigos.

Cada escolha muda o comportamento da aplicação.

---

## Critério de Escolha

Pergunte:


* a aplicação precisa de disco?
* precisa de API de objeto?
* precisa compartilhar arquivos entre máquinas?
* precisa arquivar por anos?
* precisa recuperar imediatamente?


Responder essas perguntas evita usar S3 como se fosse disco, EBS como se fosse compartilhado, ou EFS como se fosse banco.

---

## Como entender isso

Este conceito pertence ao [[Amazon S3]], serviço de armazenamento de objetos.

## Ponto central

S3 trabalha com buckets e objetos. Ele é acessado por API e é usado para arquivos, imagens, logs, backups, data lakes e conteúdo estático.

## Como Diferenciar

* S3 não é disco de EC2.
* Bucket precisa de política, criptografia e bloqueio de acesso público quando necessário.
* Classes de armazenamento mudam custo e padrão de acesso.
* Lifecycle automatiza movimentação e expiração.
* Versioning ajuda a recuperar sobrescritas e exclusões.

## Cuidado importante

S3 pode parecer uma pasta, mas internamente trabalha com objetos identificados por chaves.
