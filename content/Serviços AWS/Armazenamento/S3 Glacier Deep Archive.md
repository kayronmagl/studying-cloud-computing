S3 Glacier Deep Archive é uma classe do [[Amazon S3]] voltada para retenção de longo prazo com custo muito baixo.

É usada quando os dados quase nunca são acessados e podem esperar muitas horas para recuperação.

## Quando Usar

Use para:

* retenção fiscal;
* arquivos regulatórios antigos;
* backups de longo prazo;
* substituição de fitas;
* dados históricos;
* arquivos preservados por obrigação, não por uso operacional diário.

---

## Trade-off

Deep Archive reduz custo de armazenamento, mas aumenta tempo de recuperação.

Ele é adequado quando o objetivo é preservação, não acesso rápido.

---

## Exemplo

Uma empresa precisa guardar documentos por anos para auditoria, mas raramente consulta esses arquivos. Deep Archive pode ser adequado.

---

## Cuidado

Não use para logs recentes, dados de produção ativos, conteúdo de aplicação ou backups que precisam restauração rápida.

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
