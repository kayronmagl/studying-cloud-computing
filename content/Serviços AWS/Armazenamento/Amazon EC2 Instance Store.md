Amazon EC2 Instance Store é o armazenamento local temporário associado fisicamente ao host que executa uma instância [[Amazon EC2]].

Ele pode oferecer alta performance, mas é efêmero. Os dados podem ser perdidos quando a instância é interrompida, encerrada ou sofre falha no host, dependendo do tipo de instância e do evento operacional.

## Diferença para EBS

[[Amazon EBS]] é armazenamento em bloco persistente e independente da instância.

Instance Store é armazenamento local temporário.

A diferença principal é durabilidade.


* [[Amazon EBS|EBS]]: persistente.
* Instance Store: efêmero.


---

## Quando Usar

Instance Store pode ser útil para:

* cache temporário;
* buffers;
* arquivos intermediários;
* processamento de alta performance;
* dados que podem ser reconstruídos;
* workloads que replicam dados em outra camada.

---

## Quando Evitar

Não use Instance Store como única cópia de dados importantes.

Se o dado precisa sobreviver à falha da instância, ele deve estar em [[Amazon EBS]], [[Amazon S3]], banco gerenciado ou outra camada durável.

---

## Exemplo

Um job de processamento baixa arquivos do S3, processa localmente em disco rápido e grava o resultado final de volta no S3.

Nesse desenho, Instance Store acelera o trabalho, mas S3 preserva o dado importante.

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

---

## Pontos que Costumam Gerar Confusão

Se a instância EC2 precisa de armazenamento anexado, mas os dados são temporários e não precisam ser mantidos por longo prazo, a resposta é [[Amazon EC2 Instance Store]].

---

## Como entender

Instance Store é armazenamento local temporário associado ao host físico.

Ele pode ser rápido, mas não deve ser usado para dados persistentes.

---

## Comparação

* Instance Store: temporário.
* [[Amazon EBS]]: persistente, volume em bloco.
* [[Amazon S3]]: objetos em bucket.
* Subnet: componente de rede, não armazenamento.
