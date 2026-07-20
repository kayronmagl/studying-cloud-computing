S3 Object Lock permite proteger objetos do [[Amazon S3]] contra exclusão ou sobrescrita por um período definido ou indefinidamente.

É usado em cenários de retenção, conformidade e proteção contra alterações indevidas.

## WORM

O modelo é conhecido como Write Once, Read Many.

O dado pode ser gravado e lido, mas não modificado durante a retenção.

---

## Modos

Object Lock pode operar com modos de governança e conformidade.

O modo de conformidade é mais rígido e deve ser usado com extremo cuidado.

---

## Quando Usar

Use para:

* retenção regulatória;
* proteção contra ransomware;
* trilhas de auditoria;
* registros imutáveis;
* backup protegido.

---

## Cuidado

Configurações de retenção podem impedir exclusões legítimas.

Antes de habilitar, entenda requisitos legais, operação de recuperação e impacto de custo.

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
