Multipart Upload é o recurso do [[Amazon S3]] para enviar objetos grandes em partes.

Em vez de enviar um arquivo inteiro em uma única requisição, a aplicação divide o arquivo em partes, envia cada parte separadamente e depois conclui o upload.

## Por que Existe

Uploads grandes são mais sensíveis a falhas de rede.

Se um arquivo de muitos gigabytes falha perto do fim, reenviar tudo do zero é ineficiente.

Com multipart upload, apenas partes com falha precisam ser reenviadas.

---

## Vantagens

* melhora resiliência em uploads grandes;
* permite paralelismo;
* reduz impacto de falhas de rede;
* permite retomar partes específicas;
* melhora performance em links de alta capacidade.

---

## Fluxo

* iniciar multipart upload: ↓.
* enviar partes: ↓.
* registrar ETags das partes: ↓.
* concluir upload: ↓.
* S3 monta o objeto final


---

## Cuidado

Uploads multipart incompletos podem gerar custo.

É boa prática usar [[S3 Lifecycle]] para abortar uploads incompletos após determinado período.

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
