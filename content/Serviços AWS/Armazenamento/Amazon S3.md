Amazon S3 significa Amazon Simple Storage Service.

É o serviço de [[Armazenamento de Objetos]] da AWS. Ele guarda dados como [[Objetos S3]] dentro de [[Buckets S3]], acessados por [[APIs|API]], [[AWS SDKs|SDK]], [[AWS CLI|CLI]], console e integrações com outros serviços.

---

## O que é

Amazon S3 é o serviço de armazenamento de objetos da AWS.

Ele não é disco de servidor nem filesystem tradicional. Você armazena objetos dentro de [[Buckets S3|buckets]] e acessa via [[APIs|API]] HTTP.

---

## Por que existe

Amazon S3 existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**Modelo Mental**

S3 não é disco.

S3 é armazenamento de objetos.

Cada objeto possui chave, conteúdo, metadados, classe de armazenamento, criptografia, permissões e versão opcional.

**Buckets**

[[Buckets S3]] são contêineres lógicos e administrativos.

Eles concentram políticas, bloqueio de acesso público, lifecycle, versionamento, criptografia, logs, replicação e organização de objetos.

**Eventos**

S3 pode emitir eventos quando objetos são criados, removidos ou alterados.

Esses eventos podem acionar [[AWS Lambda]], [[Amazon SQS]], [[Amazon SNS]] ou [[Amazon EventBridge]].

Isso torna S3 muito importante em arquiteturas [[Computação sem Servidor (Serverless)|serverless]].

**Classes**

[[Classes de Armazenamento do Amazon S3]] ajudam a reduzir custo conforme o dado envelhece ou muda de padrão de acesso.

Dados quentes ficam em [[S3 Standard]]. Dados frios podem migrar por [[S3 Lifecycle]] para classes Glacier.

**Conceitos Essenciais**

* Bucket: contêiner lógico.
* Objeto: dado armazenado.
* Key: nome/caminho lógico do objeto.
* Classe de armazenamento: define custo e padrão de acesso.
* Lifecycle: move ou expira objetos automaticamente.
* Versioning: mantém versões.
* Object Lock: protege contra exclusão/sobrescrita.

**Um jeito simples de visualizar**

Pense no S3 como um lugar para guardar objetos, não como um HD.

Você não instala sistema operacional no S3. Você não anexa S3 como volume de uma instância [[Amazon EC2|EC2]]. Você coloca arquivos dentro de [[Buckets S3|buckets]] e acessa por [[APIs|API]].

**Como escolher S3**

Use S3 quando o dado é naturalmente um arquivo ou objeto:

* imagem;
* documento;
* vídeo;
* log;
* backup;
* export;
* arquivo estático;
* dataset.

**Replicação de objetos**

[[S3 Replication]] aparece quando objetos precisam ser copiados automaticamente para outro [[Buckets S3|bucket]] ou outra região.

**Escolha de armazenamento**

Antes de escolher S3, EBS ou EFS, é importante entender [[Tipos de Armazenamento da AWS]].

**Proteção e recuperação de dados**

Quando o assunto é proteção contra perda ou exclusão acidental, [[AWS Backup]] complementa serviços de armazenamento porque ajuda a centralizar políticas de backup.

---

## Exemplo prático

Uma aplicação pode usar:

* [[Amazon EBS]] para disco de uma instância;
* [[Amazon S3]] para objetos e arquivos;
* [[Amazon EFS]] para filesystem compartilhado;
* classes de armazenamento para reduzir custo de dados antigos.

Cada escolha muda o comportamento da aplicação.

Um site de catálogo pode guardar imagens dos produtos no S3.

A aplicação salva e lê essas imagens. Se quiser entregar mais rápido para usuários longe da região, pode usar [[Amazon CloudFront]] na frente.

---

## Diferenças importantes

**Critério de Escolha**

Pergunte:

* a aplicação precisa de disco?
* precisa de [[APIs|API]] de objeto?
* precisa compartilhar arquivos entre máquinas?
* precisa arquivar por anos?
* precisa recuperar imediatamente?

Responder essas perguntas evita usar S3 como se fosse disco, EBS como se fosse compartilhado, ou EFS como se fosse banco.

**Quando Usar**

* arquivos estáticos;
* imagens;
* backups;
* logs;
* data lake;
* exportações;
* conteúdo para CloudFront.

---

## Cuidados

**Segurança**

S3 exige atenção a bloqueio de acesso público, políticas de [[Buckets S3|bucket]], políticas [[AWS Identity and Access Management (IAM)|IAM]], criptografia, versionamento, logs, auditoria via [[AWS CloudTrail]] e acesso controlado por [[Amazon CloudFront]].

Um [[Buckets S3|bucket]] público indevido é um dos erros de segurança mais clássicos em nuvem.

S3 parece pasta, mas não é filesystem. Barras no nome do objeto simulam diretórios, porém o modelo real é chave-valor de objetos.

* S3: objetos.
* [[Amazon EBS|EBS]]: disco em bloco.
* [[Amazon EFS|EFS]]: arquivo compartilhado.
* [[Amazon EC2 Instance Store|Instance Store]]: temporário.

Quando o cenário envolve [[Buckets S3|bucket]], objeto ou site estático, S3 provavelmente está envolvido.

---

## Relação com outras notas

**Relação com S3 Intelligent-Tiering**

Quando objetos do S3 têm padrão de acesso imprevisível, [[S3 Intelligent-Tiering]] pode reduzir custo sem exigir escolha manual de classe.
