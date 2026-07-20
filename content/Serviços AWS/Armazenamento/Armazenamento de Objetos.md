Armazenamento de Objetos é um modelo que guarda dados como objetos independentes, cada um identificado por uma chave e acompanhado de metadados.

Na AWS, o principal serviço é o [[Amazon S3]].

## Objeto

Um objeto contém conteúdo, chave, metadados, classe de armazenamento, permissões, versão opcional e criptografia.

---

## Diferença para Bloco

[[Armazenamento em Bloco]] se comporta como disco.

Armazenamento de objetos é acessado por API.

Por isso, S3 é excelente para arquivos e dados distribuídos, mas não substitui EBS como disco de sistema operacional.

---

## Pontos Fortes

* escala massiva;
* alta durabilidade;
* metadados;
* versionamento;
* lifecycle;
* classes de armazenamento;
* integração com [[AWS Lambda]];
* entrega por [[Amazon CloudFront]].

---

## Uso Prático

É usado para imagens, vídeos, documentos, backups, logs, data lakes, exportações e conteúdo estático.

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

Este conceito pertence ao módulo de armazenamento na AWS.

## Ponto central

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via API, pense em S3. Se for filesystem compartilhado, pense em EFS ou FSx.

## Como Diferenciar

* bloco é diferente de objeto;
* objeto é diferente de arquivo compartilhado;
* classe de armazenamento altera custo e recuperação;
* lifecycle automatiza economia;
* versionamento e backup ajudam recuperação.

## Cuidado importante

Não escolha armazenamento só pelo nome do serviço. Escolha pelo padrão de acesso.
