Armazenamento de Objetos é um modelo que guarda dados como objetos independentes, cada um identificado por uma chave e acompanhado de metadados.

Na AWS, o principal serviço é o [[Amazon S3]].

---

## O que é

Armazenamento de Objetos deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via [[APIs|API]], pense em [[Amazon S3|S3]]. Se for filesystem compartilhado, pense em EFS ou FSx.

---

## Por que existe

Armazenamento de Objetos existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**Objeto**

Um objeto contém conteúdo, chave, metadados, classe de armazenamento, permissões, versão opcional e criptografia.

**Pontos Fortes**

* escala massiva;
* alta durabilidade;
* metadados;
* versionamento;
* lifecycle;
* classes de armazenamento;
* integração com [[AWS Lambda]];
* entrega por [[Amazon CloudFront]].

**Uso Prático**

É usado para imagens, vídeos, documentos, backups, logs, data lakes, exportações e conteúdo estático.

---

## Exemplo prático

Uma aplicação pode usar:

* [[Amazon EBS]] para disco de uma instância;
* [[Amazon S3]] para objetos e arquivos;
* [[Amazon EFS]] para filesystem compartilhado;
* classes de armazenamento para reduzir custo de dados antigos.

Cada escolha muda o comportamento da aplicação.

---

## Diferenças importantes

**Diferença para Bloco**

[[Armazenamento em Bloco]] se comporta como disco.

Armazenamento de objetos é acessado por [[APIs|API]].

Por isso, [[Amazon S3|S3]] é excelente para arquivos e dados distribuídos, mas não substitui EBS como disco de sistema operacional.

**Critério de Escolha**

Pergunte:

* a aplicação precisa de disco?
* precisa de [[APIs|API]] de objeto?
* precisa compartilhar arquivos entre máquinas?
* precisa arquivar por anos?
* precisa recuperar imediatamente?

Responder essas perguntas evita usar [[Amazon S3|S3]] como se fosse disco, EBS como se fosse compartilhado, ou EFS como se fosse banco.

**Como Diferenciar**

* bloco é diferente de objeto;
* objeto é diferente de arquivo compartilhado;
* classe de armazenamento altera custo e recuperação;
* lifecycle automatiza economia;
* versionamento e backup ajudam recuperação.

---

## Cuidados

Não escolha armazenamento só pelo nome do serviço. Escolha pelo padrão de acesso.

---

## Relação com outras notas

- [[Amazon S3]]
- [[AWS Lambda]]
- [[Amazon CloudFront]]
- [[Amazon EBS]]
- [[Amazon EFS]]
- [[Armazenamento em Bloco]]
