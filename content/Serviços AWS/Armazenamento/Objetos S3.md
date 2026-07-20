Objetos S3 são as unidades de dado armazenadas no [[Amazon S3]].

Um objeto não é apenas o arquivo. Ele inclui conteúdo, chave, metadados e propriedades de armazenamento.

## Componentes

Um objeto possui:

* chave;
* dados;
* metadados;
* ETag;
* classe de armazenamento;
* criptografia;
* versão opcional;
* tags opcionais.

---

## Chave

A chave identifica o objeto dentro do bucket.

Exemplo:


* relatorios/2026/janeiro.pdf


Essa estrutura parece diretório, mas é uma chave textual com barras. S3 não é filesystem tradicional.

---

## Metadados

Metadados descrevem o objeto.

Eles podem incluir tipo de conteúdo, tamanho, informações de cache, criptografia, tags e dados customizados.

---

## Relação com APIs

Objetos são enviados, lidos e removidos por APIs.

Isso diferencia S3 de [[Amazon EBS]] e [[Amazon EFS]]. A aplicação precisa pensar em operações de objeto, não em blocos de disco ou diretórios montados.

---

## Exemplo Arquitetural

Uma aplicação pode salvar imagens originais como objetos S3, gerar miniaturas com [[AWS Lambda]] e distribuir o conteúdo por [[Amazon CloudFront]].

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
