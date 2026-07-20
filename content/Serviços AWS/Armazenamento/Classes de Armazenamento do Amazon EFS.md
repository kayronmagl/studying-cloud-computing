Classes de Armazenamento do Amazon EFS permitem otimizar custo conforme o padrão de acesso dos arquivos.

Arquivos frequentemente acessados permanecem em camadas de acesso rápido. Arquivos menos acessados podem ser movidos para camadas mais econômicas.

## Por que Importa

Filesystems compartilhados podem acumular dados antigos.

Sem política de ciclo de vida, arquivos frios continuam custando como dados ativos.

---

## Cuidado

Mover arquivos para classes frias pode afetar latência no primeiro acesso.

---

## Lifecycle no EFS

As classes de armazenamento do EFS são mais úteis quando o filesystem acumula dados com diferentes temperaturas de acesso.

Arquivos recentes podem permanecer em classe de acesso frequente. Arquivos antigos podem migrar para classes mais baratas conforme políticas de lifecycle.

---

## Relação com Custo

Sem lifecycle, um filesystem compartilhado pode crescer durante anos e manter todo dado em uma camada cara.

Com lifecycle, o custo acompanha melhor o uso real.

---

## Cuidado na prática

O primeiro acesso a dados frios pode ter latência diferente. A aplicação precisa tolerar esse comportamento.

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
