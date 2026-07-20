S3 One Zone-IA é uma classe do [[Amazon S3]] para dados de acesso infrequente armazenados em uma única [[Availability Zones (AZ)|Availability Zone]].

Ela custa menos que classes multi-AZ, mas tem menor resiliência contra perda de zona.

## Quando Usar

Use para dados que podem ser recriados:

* thumbnails;
* caches persistentes;
* dados derivados;
* cópias secundárias;
* arquivos temporários importantes, mas reconstruíveis.

---

## Pergunta Decisiva

* posso reconstruir esse dado se a zona falhar?


Se a resposta for não, One Zone-IA pode ser inadequado.

---

## Exemplo

Miniaturas de imagens podem ficar em One Zone-IA se a aplicação mantém os arquivos originais em S3 Standard e consegue gerar miniaturas novamente.

---

## Cuidado

Não use para única cópia de dados críticos, regulatórios ou irrecuperáveis.

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
