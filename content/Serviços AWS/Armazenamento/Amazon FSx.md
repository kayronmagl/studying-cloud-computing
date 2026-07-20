Amazon FSx é uma família de serviços AWS para sistemas de arquivos gerenciados especializados.

Enquanto [[Amazon EFS]] fornece filesystem elástico para workloads Linux via NFS, FSx oferece opções para necessidades específicas.

## Opções

* FSx for Windows File Server;
* FSx for Lustre;
* FSx for NetApp ONTAP;
* FSx for OpenZFS.

---

## Windows File Server

Usado quando aplicações precisam de compartilhamento SMB, integração com Windows e Active Directory.

---

## Lustre

Usado para HPC, machine learning, processamento intensivo e datasets de alta performance.

---

## ONTAP e OpenZFS

Usados quando a aplicação precisa de recursos avançados de filesystem corporativo, snapshots, clones, replicação e compatibilidade específica.

---

## Decisão

Use FSx quando o workload exige um filesystem especializado.

Use [[Amazon EFS]] quando precisa de filesystem Linux elástico e compartilhado.

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
