Snapshots do Amazon EBS são cópias de backup de [[Volumes do Amazon EBS]].

Eles permitem restaurar volumes, criar cópias, migrar dados e compor estratégias de [[Disaster Recovery (DR)]].

## Incrementalidade

Depois do primeiro snapshot, snapshots posteriores armazenam blocos alterados.

Isso reduz duplicação e custo em backups recorrentes.

---

## Uso Prático

Snapshots servem para backup, restauração, cópia entre regiões, criação de novos volumes, proteção antes de mudanças críticas e recuperação de ambiente.

---

## Consistência

Para bancos de dados, snapshot precisa considerar consistência.

Se há escrita em andamento, pode ser necessário pausar aplicação, usar ferramentas do banco, congelar filesystem ou coordenar múltiplos volumes.

---

## Limite Conceitual

Snapshot de volume não é backup completo de aplicação.

Uma aplicação pode depender de S3, RDS, filas, IAM, VPC e configurações externas. Recuperação real precisa considerar todos os componentes.

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
